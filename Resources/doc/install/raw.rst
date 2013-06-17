Install in a boilerplate application
------------------------------------

Not everybody is using Symfony2 framework and some people might
need an integration of this bundle within a custom installation.

Gitonomy GitBundle gives you possibility to reuse Twig code
without the bundle integration.

To do so, make sure you have enabled autoloading of bundle classes.

When it's done, add the extension to your Twig:

.. code-block:: php

    use Gitonomy\Bundle\GitBundle\Twig\GitExtension;
    use Gitonomy\Bundle\GitBundle\Routing\GitUrlGeneratorInterface;
    use Symfony\Component\Routing\UrlGeneratorInterface;

    $router instanceof UrlGeneratorInterface;

    $generator = new GitUrlGenerator($router);
    $extension = new GitExtension($generator, array(
        '@GitonomyGitBundle/default_theme.html.twig'
    ));

    $twig->addExtension($extension);
    $twig->addPath('/path/to/Gitonomy/Bundle/GitBundle/Resources/views', '@GitonomyGitBundle');

