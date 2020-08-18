## Building Container images using Declarative approach

docker build -t [IMAGENAME] [DIR-PATH]

IMAGENAME:	The NEW Image Name (Unique)
DIR-PATH:	Relative or Absolute path to 
		folder which containers "Dockerfile"

Example [Assumming, current directory is d:\git\docker-aug-2020\simple-dockerfile] :
docker build -t myapp1 $PWD
docker build -t myapp1 . 
docker build -t myapp1 d:\git\docker-aug-2020\simple-dockerfile


