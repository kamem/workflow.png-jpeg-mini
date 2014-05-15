workflow.png-jpeg-mini
======================

jpegoptim → ImageOptim or  ImageAlpha → ImageOptim を拡張子にわけてショートカットを割り当てて手軽にできる


	for f in "$@"
	do
		[ `basename "$f" .png` = `basename "$f"` ] || {
			/Applications/ImageAlpha.app/Contents/Resources/pngquant --speed 3 --force --ext .png 256 "$f"; open -a imageoptim "$f"
	
	       	}
	
		[ `basename "$f" .jpg` = `basename "$f"` ] || {
			/usr/local/bin/jpegoptim --strip-all --max=40 "$f"; open -a imageoptim "$f"
	
	       	}
	done