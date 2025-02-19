==========================
ascl_net_scraper
==========================

.. image:: https://img.shields.io/pypi/v/ascl_net_scraper
   :alt: PyPI Package
   :target: https://pypi.org/project/ascl_net_scraper
.. image:: https://img.shields.io/pypi/dm/ascl_net_scraper
   :alt: PyPI Downloads
   :target: https://pypi.org/project/ascl_net_scraper
.. image:: https://img.shields.io/pypi/l/ascl_net_scraper
   :alt: License
   :target: https://github.com/charmoniumQ/ascl_net_scraper/blob/main/LICENSE
.. image:: https://img.shields.io/pypi/pyversions/ascl_net_scraper
   :alt: Python Versions
   :target: https://pypi.org/project/ascl_net_scraper
.. image:: https://img.shields.io/librariesio/sourcerank/pypi/ascl_net_scraper
   :alt: libraries.io sourcerank
   :target: https://libraries.io/pypi/ascl_net_scraper
.. image:: https://img.shields.io/github/stars/charmoniumQ/ascl_net_scraper?style=social
   :alt: GitHub stars
   :target: https://github.com/charmoniumQ/ascl_net_scraper
.. image:: https://github.com/charmoniumQ/ascl_net_scraper/actions/workflows/main.yaml/badge.svg
   :alt: CI status
   :target: https://github.com/charmoniumQ/ascl_net_scraper/actions/workflows/main.yaml
.. image:: https://img.shields.io/github/last-commit/charmoniumQ/charmonium.determ_hash
   :alt: GitHub last commit
   :target: https://github.com/charmoniumQ/ascl_net_scraper/commits
.. image:: http://www.mypy-lang.org/static/mypy_badge.svg
   :target: https://mypy.readthedocs.io/en/stable/
   :alt: Checked with Mypy
.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
   :target: https://github.com/psf/black
   :alt: Code style: black

Scrapes the data from https://ascl.net


----------
Quickstart
----------

If you don't have ``pip`` installed, see the `pip install
guide`_.

.. _`pip install guide`: https://pip.pypa.io/en/latest/installing/

.. code-block:: console

    $ pip install ascl_net_scraper

>>> from rich.pretty import pprint # for pretty printing
>>> import ascl_net_scraper
>>> codes = ascl_net_scraper.scrape_index(5)
>>> pprint(codes[0]) # doctest: +ELLIPSIS
CodeRecord(
│   ascl_id=None,
│   title='2-DUST: Dust radiative transfer code',
│   credit=['Ueta, Toshiya'],
│   abstract='<p>...</p>',
│   details_url='https://ascl.net/1604.006'
)
>>> pprint(codes[0].get_details(), max_string=70) # doctest: +ELLIPSIS
DetailedCodeRecord(
│   ascl_id=None,
│   title='2-DUST: Dust radiative transfer code',
│   credit=['Ueta, Toshiya'],
│   abstract='<p>2-DUST is a general-purpose dust radiative transfer code for an axi'+319,
│   url='https://ascl.net/1604.006',
│   code_sites=['https://github.com/sundarjhu/2-DUST/'],
│   used_in=['https://ui.adsabs.harvard.edu/abs/2004ApJ...614..371M'],
│   described_in=['https://ui.adsabs.harvard.edu/abs/2003ApJ...586.1338U'],
│   bibcode='2016ascl.soft04006U',
│   preferred_citation_method='<p><a href="https://ui.adsabs.harvard.edu/abs/2003ApJ...586.1338U">htt'+58,
│   discuss_url='/phpBB3/viewtopic.php?t=33976',
│   views=...
)
>>> # "github" is a special computed attribute:
>>> codes[0].get_details().github
'https://github.com/sundarjhu/2-DUST/'
