{{cookiecutter.package_name}}.sif: makefile image.def
	singularity build --fakeroot {{cookiecutter.package_name}}.sif image.def
build: {{cookiecutter.package_name}}.sif
run: build
	singularity shell {{cookiecutter.package_name}}.sif
