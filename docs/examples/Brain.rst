======================================
Basic Brain Examples
======================================

Basic Reading
-------------

Setting the cursor does xxx

..
    .. literalinclude:: ../../examples/basic_reads.py
        :pyobject: read_single

    >>> set_cursor()
    Tag(tag='DINT1', value=20, type='DINT', error=None)

Printing does xxx

..

    .. literalinclude:: ../../examples/basic_reads.py
        :pyobject: read_multiple

    >>> read_multiple()
    [Tag(tag='DINT1', value=20, type='DINT', error=None), Tag(tag='SINT1', value=5, type='SINT', error=None), Tag(tag='REAL1', value=100.0009994506836, type='REAL', error=None)]

