Advanced Configuration
======================

Full configuration options:

.. code-block:: yaml

    fos_user:
        db_driver:        orm # can be orm or odm
        firewall_name:    main
        user_class:       Application\Sonata\UserBundle\Entity\User

        group:
            group_class:  Application\Sonata\UserBundle\Entity\Group

        profile:  # Authentication Form
            form:
                type:               fos_user_profile
                handler:            fos_user.profile.form.handler.default
                name:               fos_user_profile_form
                validation_groups:  [Authentication] # Please note : this is not the default value

    sonata_user:
        security_acl:           false
        impersonating_route:    homepage # or any route you want to use
        class:
            user:               Application\Sonata\UserBundle\Entity\User
            group:              Application\Sonata\UserBundle\Entity\Group

        profile:  # Profile Form (firstname, lastname, etc ...)
            form:
                type:               sonata_user_profile
                handler:            sonata.user.profile.form.handler.default
                name:               sonata_user_profile_form
                validation_groups:  [Profile]

    # Enable Doctrine to map the provided entities
    doctrine:
        orm:
            entity_managers:
                default:
                    mappings:
                        FOSUserBundle: ~
                        ApplicationSonataUserBundle: ~
                        SonataUserBundle: ~
