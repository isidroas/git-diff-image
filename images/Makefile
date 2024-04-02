earth.jpg:
	curl https://www.nasa.gov/wp-content/uploads/2023/03/135918main_bm1_high.jpg -o $@
	# curl https://upload.wikimedia.org/wikipedia/commons/9/97/The_Earth_seen_from_Apollo_17.jpg -o $@

example-comparison.png: earth.jpg earth_with_label.jpg
	../diff-image -o $@   $^
	# ../diff-image -o $@   earth.jpg  earth_with_label.jpg
	# ../diff-image   $^


earth_with_label.jpg: earth.jpg
	# convert -pointsize 20 -fill yellow -draw 'text 270,460 "Sunset over the Nile" ' $^ $@

	# convert $^ -gravity South -pointsize 22  -fill white -annotate +30+30  "%[exif:DateTimeOriginal]" $@
	# source https://superuser.com/a/649078

	convert $^ -gravity South -pointsize 60  -undercolor white -stroke gray -fill gray -annotate +30+30 'The earth seen from Apollo 17' $@
	# convert $^ -gravity South -pointsize 80  -undercolor white -stroke gray -fill gray :label 'The earth seen from Apollo 17' $@

  # TODO: margins
  # https://imagemagick.org/script/command-line-options.php?#undercolor
  # https://imagemagick.org/script/command-line-options.php?#draw
  # https://imagemagick.org/script/command-line-options.php?#annotate
  # https://imagemagick.org/Usage/text/
	# convert $^ -gravity South -pointsize 60  -undercolor white -stroke gray -fill gray -draw 'text 0,0 "The earth seen from Apollo 17"' $@
