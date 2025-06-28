# Add another language

We love adding more languages to this prebuild!
 
1. Add the language to the `languages` attribute in `gazelle_binary` in `BUILD`
1. We'll check if the binary size explodes - in that case it might need some more thought.
1. If the extension isn't self-contained (e.g. depends on node binary) then it needs careful docs, or a way to statically-link it into the go binary.

# Releasing

1. Push to the release branch: `git push <release commit> HEAD:release`
2. Wait for the release workflow to run
3. You're done!

The release workflow will create a tag and release on GitHub.

