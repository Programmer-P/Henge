# Henge — personal fork of upstream Henge

The user-facing name is Henge. The project follows Leviidev/Henge and retains upstream GPL licensing and naming. The previous experimental name PocketMac is retired.

The source ios/project.yml now uses the upstream defaults: Henge and com.henge.app. Existing iPhone and iPad Henge installations use com.programmerp.henge and contain virtual machine and app data. To update while preserving that data, override the bundle ID at build/sign time with HENGE_BUNDLE_IDENTIFIER=com.programmerp.henge, keep the original signing team and entitlements, and verify the package first. An install with com.henge.app is a different app and does not preserve the old sandbox.

Code2Go is a separate developer IDE app. The file handoff and guest-only QA gates are documented in docs/code2go-integration.md. Guest Swift and full Xcode have not yet been verified. Do not alter or delete macOS guest disks while rebranding.
