## hawtio release guide

The following walks through how we make a release.

* Pop onto [IRC](http://hawt.io/community/index.html) and let folks know you're about to cut a release
* Now pull and make sure things build locally fine first :)

		mvn release:prepare -P release,grunt

If the build fails then rollback via

    mvn release:rollback -P release,grunt

The tag should get auto-defaulted to something like **hawtio-1.2**

		mvn release:perform -P release,grunt

when the release is done:

		git push --tags

Now go to the [OSS Nonatype Nexus](https://oss.sonatype.org/index.html#stagingRepositories) and Close then Release the staging repo

Now update the new dev version in [SpecRunner.html](https://github.com/hawtio/hawtio/blob/master/hawtio-web/src/test/specs/SpecRunner.html#L88) so the new dev build doens't barf

Now drink a beer! Then another! There, thats better now isn't it!




