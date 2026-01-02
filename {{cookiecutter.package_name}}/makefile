{{cookiecutter.package_name}}.sif: makefile image.def
	singularity build --fakeroot {{cookiecutter.package_name}}.sif image.def
build: {{cookiecutter.package_name}}.sif
{% if cookiecutter.rich_console=='y' %}
run: build
	singularity exec --bind ./notebooks:/apps/notebooks --bind ./container_bashrc:/apps/container_bashrc {{cookiecutter.package_name}}.sif /bin/bash --rcfile /apps/container_bashrc
{% else %}
run: build
	singularity shell --bind ./notebooks:/apps/notebooks  {{cookiecutter.package_name}}.sif
{% endif %}
