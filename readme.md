# Pictoprime 

This is a program used to generate prime numbers from pictures.

## Dependencies 

Ensure you have the following dependencies:

- [Node.js](https://nodejs.org/en/download/) (16+ supported, earlier versions will also likely work)
- [GraphicsMagick](https://github.com/IonicaBizau/image-to-ascii/blob/HEAD/INSTALLATION.md)
- OpenSSL ([Windows](https://wiki.openssl.org/index.php/Binaries)) (Mac / Linux likely already have it)

GraphicsMagick Common Installations: 
```
# OS X
brew install graphicsmagick

# Windows users can install the binaries from http://www.graphicsmagick.org/ or using the command line:
choco install graphicsmagick
```

## To Install
You can install this program just by running: 
```
npm i -g pictoprime 
```





## To Run
```
$ pictoprime --help
Usage: pictoprime [options]

A program to find picture-esque primes. Requires openssl.

Options:
  -V, --version          output the version number
  -n, --number <number>  The number to be transformed into a prime.
  -i, --image <image>    Use an image to find primes.
  -q, --quiet            Hides some of the debug information to make it easier to get output from this program.
  -x, --export <mode>    The output format (choices: "json", "prime", "ascii", default: "json")
  --pixels <pixels>      The numbers to use to generate the prime (image mode). Left side is lighter, right side is darker. (default: "7772299408")
  --width <width>        The width of the ascii to generate (image mode). (default: "32")
  --contrast <contrast>  Additional contrast to apply between -1.0 and 1.0 (image mode). (default: "0.1")
  -s, --sophie           Enable the search for an (almost) Sophie Germain prime (useful for Discrete Log cryptography).
  -h, --help             display help for command
  ```

### Example 

```
pictoprime -i examples/headshot.png
{
  prime: '888888888888888888880499222229999999400888888888888888888888888888888888888888888049222222222222299999994888888888888888888888888888888888888884922227777722222222222992294088888888888888888888888888888888809277777777777772222222222222290088888888888888888888888888888092777777777777777777777722222222940888888888888888888888888888427777777777777777777777777222222299088888888888888888888888888827777777777777777777777777222222222948888888888888888888888888847777777777777777777777777222222222999888888888888888888888888882777777777777777777777777722222222299908888888888888888888888880777777777777777777777777777722222299994888888888888888888888888027777777777777777777777772222222222299488088888888888888888888884777777777777777777777222222999922229944994888888888888888888888897777222277777777777772222222299222999229908888888888888888888880277227777777777777222929999922222229922994888888888888888888842927777722292227777229227299292222222999992488888888888888888880277777722794922777722222222222227722299999208888888888888888888827777777772227777772222222227777722229999220888888889888888888889777777777777777777222222777777722222999222088888888888888888888477777777777777717722222177777772222229400088888888888888888888807717777777777777772222227777777222222208888888888888888888888888922777777777777777222229277777222222224888888888888888888888888888097777777777727729992222777722222222488888888888888888888888888880777777777777772222222222271292722298888888888888888888888888888827777777777777777222999227722222224888888888888888888888888888889777777727777772222222222772222229888888888888888888888888888888027777777777772222222222222222299088888888888888888888888888888880977777777777777772222222292999248888888888888888888888888888888884277777777777777722229999999224888888888888888888888888888888888802777777777777722229999992222948888888888888888888888888888888888277227772222222299999922222222488888888888888888888888888888888827777772222222222222222222222298888888888888888888888888888888802777177777777772222222777222229888888888888888888888888888888884777777777777777722227777777777988888888888889',
  attempts: 382,
  simultaneous: 10,
  distinctTested: 3830
}
```

<img alt="A picture of matt parker's face" src="examples/headshot.png" width=256 height=256 />
<img alt="A picture of matt parker's face but as a prime number." src="examples/output.png" width=256 height=256 />


## To Develop

Clone the repository and run:
```
yarn
```
then 
```
node index.js 
```

## Special Thanks To

- Numberphile, JF Mckee for [their video on the Trinity Hall Prime](https://www.youtube.com/watch?v=fQQ8IiTWHhg), inspiring earlier versions of this project.
- Matt Parker, for being a brilliant maths educator & inspiring amateur mathematicians to give things a try. :) 
- [Forbes Lindesay](https://github.com/ForbesLindesay), for their optimization contributions. 
