.. _manual_platform_sdk_getting_started:

Getting Started
===============

Before you can use the Platform SDK, you need to:

1. `Create a developer account <https://developer.oculus.com/sign-up/>`_ for Meta Quest.
2. Create an app within the Meta Quest `Developer Dashboard <https://developer.oculus.com/manage/>`_.
3. Visit the "API" tab within the developer dashboard for your app, and make note of your "App ID" - you'll need this to initialize the Platform SDK.
4. Make a release build of your application, using the real "Unique Name" and release keystore. At this point, your application probably doesn't do much, which is fine.
5. Upload this build using the `Meta Quest Developer Hub <https://developer.oculus.com/meta-quest-developer-hub/>`_ to the ALPHA channel.
6. Complete a `Data Use Checkup <https://developer.oculus.com/resources/publish-data-use/>`_ (DUC), including all the features of the Platform SDK you intend to use. You won't have access to any features you don't include in your DUC.
7. Wait for your DUC to be approved.

After that process is complete, you'll be able to use the Platform SDK:

.. code-block:: gdscript

    func setup_meta_platform_sdk():
        var result: MetaPlatformSDK_Message

        # Replace "1234" with your App ID.
        result = await MetaPlatformSDK.initialize_platform_async("1234").completed
        if result.is_error():
            print("Unable to initialize the platform SDK: ", result.error)
            return

        # Check that the user owns this app and is entitled to use it.
        result = await MetaPlatformSDK.entitlement_get_is_viewer_entitled_async().completed
        if result.is_error():
            print("The user isn't entitled: ", result.error)
            return

        # Get the list of the user's friends who also own this app.
        # NOTE: This will only work if you requested access to "Friends" on your DUC (see earlier instructions).
        result = await MetaPlatformSDK.user_get_logged_in_user_friends_async().completed
        if result.is_error():
            print("Unable to get friends: ", result.error)
            return

        print("My friends:")
        for user in result.data:
            print("- ", user)

For more information, see the API docs for the :ref:`MetaPlatformSDK<class_metaplatformsdk>` singleton. It's the entry point for doing anything with the Meta Platform SDK.
