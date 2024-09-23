xpinyin-plus
==========

.. image:: https://img.shields.io/pypi/v/xpinyin.svg
    :target: https://pypi.python.org/pypi/xpinyin/

.. image:: https://img.shields.io/pypi/dm/xpinyin.svg
    :target: https://pypi.python.org/pypi/xpinyin/

xpinyin-plus 是在 xpinyin 基础上修改维护的 Python 包，提供汉字到拼音的转换。

xpinyin-plus is a Python package modified and maintained based on xpinyin, offering conversion from Chinese characters to pinyin.


Install 安装
----------

Python version >= 3.6

.. code-block:: python

    pip install -U xpinyin


**xpinyin-plus 不再向 Python 版本低于 3.6 的用户提供支持，若您有该需求，请使用 xpinyin。**

**xpinyin-plus no longer provides support for users with Python versions below 3.6. If you require such support, please use xpinyin.**


Usage 使用方式
-----

.. code-block:: python

    >>> from xpinyin import Pinyin
    >>> p = Pinyin()
    >>> # default splitter is `-`
    >>> p.get_pinyin("上海")
    'shang-hai'
    >>> # show tone marks
    >>> p.get_pinyin("上海", tone_marks='marks')
    'shàng-hǎi'
    >>> p.get_pinyin("上海", tone_marks='numbers')
    >>> 'shang4-hai3'
    >>> # remove splitter
    >>> p.get_pinyin("上海", '')
    'shanghai'
    >>> # set splitter as whitespace
    >>> p.get_pinyin("上海", ' ')
    'shang hai'
    >>> p.get_initial("上")
    'S'
    >>> p.get_initials("上海")
    'S-H'
    >>> p.get_initials("上海", '')
    'SH'
    >>> p.get_initials("上海", ' ')
    'S H'
    >>> # get_initials with retroflex, #39
    >>> p.get_initials("上海", splitter='-', with_retroflex=True)
    'SH-H'
    >>> # New in version 0.7.0, get combinations of the multiple readings of the characters
    >>> p.get_pinyins('模型', splitter=' ', tone_marks='marks')
    ['mó xíng', 'mú xíng']
    >>> p.get_pinyins('模样', splitter=' ', tone_marks='marks')
    ['mó yáng', 'mó yàng', 'mó xiàng', 'mú yáng', 'mú yàng', 'mú xiàng']
