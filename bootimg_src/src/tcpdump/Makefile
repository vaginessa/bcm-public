all: ../../bin/tcpdump

../../bin/tcpdump: libs/armeabi/tcpdump
	cp libs/armeabi/* ../../bin
	cp $< ../../../androidstudioprojects/Nexmon/app/src/main/res/raw

libs/armeabi/tcpdump: Android.mk ../libpcap/local/armeabi/libpcap.a
	$(NDK_ROOT)/ndk-build NDK_APPLICATION_MK=`pwd`/Application.mk NDK_APP_OUT=. TARGET_PLATFORM=android-21

../libpcap/local/armeabi/libpcap.a: FORCE
	cd ../libpcap && make

../shared_system_libs/libssl.so: FORCE
	cd ../shared_system_libs && make

clean:
	rm -Rf libs
	rm -Rf local

FORCE:
