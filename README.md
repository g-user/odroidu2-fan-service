This is a small C project for the ODROID-U2 Platform by Hardkernel, originally by mdrjr and previously tweaked by severnt.

This will behave like a service running on background, checking the current SoC temperature and based on that, set the fan PWM controller on U2.

By default it understands that the maximum cpu temperature that can be achieved without throttle is 85C,
so, knowning that we setted a limit of 80C where at 80C fan speed will be at max.

My goal here was to tweak the thresholds to my liking.

# Requirements:

1. `build-essential` and `git` packages.

	sudo apt-get install build-essential git

2. ODROID-U2 running Ubuntu, fan connected to the two pin header near the power jack


# Installing

	# Clone only the latest commit
	git clone --depth 1 https://github.com/rcarmo/odroidu2-fan-service.git
	cd odroidu2-fan-service
	make
	# Install upstart service and the program to /bin
	make usi
