# cpython-template

export FLASK_APP=main
export FLASK_ENV=development

flask run

docker build -t rg.fr-par.scw.cloud/xussof/python-template app/

docker push -t rg.fr-par.scw.cloud/xussof/python-template

docker run -it --name python-template rg.fr-par.scw.cloud/xussof/python-template bash