# Prebuilt APK to be used with my AuroraStore-AuroraDroid-AppWarden "FatAurora" branch

This is a collection of FOSS APKs, coupled with the respective Android.mk for an easy integration in the Android build system. These are just the official unmodified prebuilt binaries, signed by the corresponding developers, except for:

    com.google.android.maps, as the JAR and the XML have been extracted from the ZIP on the microG's GitHub release page


 Include this repo into your local manifest (path does not matter, suggest prebuilts/SuperFatAurora)
 Specify PRODUCT_PACKAGES += AuroraStore AuroraServices AuroraDroid AppWarden eSpeakTTS in a 'product' .mk file (not in an Android.mk file like SuperFatAurora.mk)
 An 'elegant' way to do so without having to fork and track any specific device or vendor repository is to simply create a SuperFatAurora.mk file in directory vendor/extras (or to add the above statement into an existing one).

The included APKs are:
 * microG packages (binaries sourced from [here](https://microg.org/download.html) and [here](https://github.com/microg/android_frameworks_mapsv1))
   * GmsCore: the main component of microG, a FOSS reimplementation of the Google Play Services (requires GsfProxy and FakeStore for full functionality)
   * GsfProxy: a GmsCore proxy for legacy GCM compatibility
   * FakeStore: a SuperFake package that does what is needed
   * com.google.android.maps: legacy microG's mapsv1 reimplementation
