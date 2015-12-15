<section>
          <section data-markdown>
            <script type="text/template">
              ## Why we chose Grav for http://ndlc.ingo
              ### general concepts
              * everything in code via Git
              * simplicity vs complexity
              * simple deployment with Ansible
              * buildable via cli utility - `bin/grav install`
              * good documentation
              * flexible front-end
              * fast prototyping
            </script>
          </section>
          <section data-markdown>
            <script type="text/template">
              ## Requirements
              * a few pages
              * a few editors
              * timely content review by non-tenical user
              * form submissions with file uploads
              * clean simple design
              ## Users
              * info seekers
              * talk submitters
              * developers
                * as programmers
                * as content creators
              * system administrators
            </script>
          </section>
          <section data-markdown>
            <script type="text/template">
              ## How Grav + Ansible == WIN!
              Grav is PHP so the team feels comfortable with it, but there are new things to learn like:
              * working with Symfony, a PHP framework that Drupal 8 uses
              * working with Composer, a PHP library dependence manager
              ### Automation with Ansible
              * server only requires SSH
              * all server configureations done via Ansible so it is in git and version control
              * same local setups as production
            </script>
          </section>
          <section data-markdown>
            <script type="text/template">
              ## Known Unknowns
              I knew there would be something that would come up, just not sure what it would be.
              ### File uploads
              One of the risks of choosing a young framework like Grav is may not be support for things that more established frameworks have, like file uploads. Grav has a very robust form API but did not support file uploads at the time of creating the site. It does now _(was added a few weeks ago)_
              **Opportunitity** - we took this as a challenge to learn the Grav plugin system and write our own file upload plugin
              #### what we learned
              * how Grav hooks work
              * review of how files get uploaded via PHP
              ### Ansible issues
              Ansible also had a bit of a learning curve, so better to learn on a system that has less moving parts than something like Drupal.
              * **Strange error reporting** - Ansible was reporting SSH errors that turned out to actually be file permissions
            </script>
          </section>
          <section data-markdown>
            <script type="text/template">
            ## Benefits outweighted the Risks
            ### Benefits
            * New lessons learned with using the tools yielded a greater understanding:
              * Object Oriented PHP coding with Grav
              * Ansible deployments - tracked with git
              * SASS
              * Bootstrap - extended with subthemes in Grav
              * Git as a deployment workflow
            ### ~Risks~ err Opportunities
            * Getting things like Grav cli install errors on Ansible deployment
              * turned out to be a bug in Composer using too much memory
              * we are currently stuck on Grav 1.0-rc2 because of this
            </script>
          </section>
        </section>