# Fluid Quadratic Funding

This is an open-source implementation of "fluid quadratic funding," a continuous form of public goods funding that 
leverages quadratic funding formulas and programmable cashflows to automatically distribute funds among recipients in an
equitable way. 

[Quadratic Funding](https://vitalik.ca/general/2019/12/07/quadratic.html) is a mechanism designed to provide matching funds 
or subsidies to (public goods) projects based on 
user donation activity. By design, this is inherently a discrete process: after a fixed amount of time (a
grant round, say), all donations for all projects are aggregated according to the QF formula and matching funds from a
matching fund pool are distributed according to the formula. For more information on how this works in 
the exemplar QF public goods funding implementation, see [Gitcoin Grants – Quadratic Funding for the World](https://gitcoin.co/blog/gitcoin-grants-quadratic-funding-for-the-world/) 
This model does not quite work for Artizen Grants, which
can have arbitrary start and end datetimes, and so we sought a more continuous or "fluid" approach. Additionally, we
wanted a highly accurate, real-time representation of the impact of a new donation in order to provide the donor with a
great user experience. With a monolithic, discrete funding round, it's impossible to give an accurate match estimate
to a user---essentially, one cannot predict the future. (Will this new donation be the last donation this round? Or will there be 10k
more donations of $100k each??) With our proposed fluid funding model, one can say with a higher degree of accuracy 
precisely what impact a new donation has on a grant's match funding stream.

## Project overview

This project will contain a simple overview of a basic fluid funding model as well as a proof-of-concept implementation. 
Internally at [Artizen](https://artizen.fund/), our goal for this fluid QF project is to help inform how Artizen Grants 
will receive real-time match funding based on donations to those grants. [Artizen's mission](https://www.artizen.fund/mission) 
is to build the largest community fund for public goods.

The abstract fluid funding model is flexible, but in this project, we will primarily focus on quadratic funding-like formulas. For 
more information on quadratic funding (abbreviated QF below), please see:

* [*Liberal Radicalism: A Flexible Design For Philanthropic Matching Funds* by Buterin, Hitzig, and Weyl](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3243656)
* [Vitalik Buterin's blog post "Quadratic Payments: A Primer"](https://vitalik.ca/general/2019/12/07/quadratic.html)
* [Gitcoin's wtfisqf.com](https://wtfisqf.com/)
* [Gitcoin's gitcoinco/quadratic-funding Additional Reading list](https://github.com/gitcoinco/quadratic-funding#additional-reading)

We acknowledge that (and express our appreciation and gratitude! 🙌 ) [Gitcoin Grants](https://gitcoin.co/grants/) has 
developed an open-source implementation of quadratic funding to provide matching funds for donations, and as of the 
initial draft of this document (June 2022), Gitcoin Grants have completed 13 rounds of crowdfunding. (In fact, this 
fluid QF project is in the process of submitting a grant for Gitcoin GR14!)

Gitcoin has a fantastic introduction to applying QF in these contexts under their ["How Does it Work?" section of the README in gitcoinco/quadratic-funding](https://github.com/gitcoinco/quadratic-funding#how-does-it-work).

## Rough projected timeline

### Summer 2022

* Create Gitcoin Grant
* Documentation: draft docs describing model (wiki)
* Experiments: create jupyter notebooks for fluid QF model simulations and analysis (python)
* Proof-of-concept: build first prototype (solidity, typescript)
  * Initial prototype will likely involve Superfluid Instant Distribution Agreements (IDAs) and be built on Polygon 

### Fall 2022

* Integrate with Artizen Grant web3 system