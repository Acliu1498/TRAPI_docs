.. _chunks:

Chunks
------

Each project is separated into smaller chunks, which the user records. The recorded chunks are later put together to create the finished project. Each chunk requires the following:

- ``start``: the beginning unit number of the chunk

- ``end``: the end unit number of the chunk

- ``sort``: the chunk number

The default chunk is one unit of the smallest division of the source text (e.g. the smallest division of the Bible is verses, so the default chunk would be one verse).

**Example:**

.. code-block:: yaml

    {

      "chunks": [{

                     start: 1

                     end: 1

                     sort: 1

                 },

                 {
                     start: 2

                     end: 2

                     sort: 2

                 },

                 {
                    start: 3

                     end: 3

                     sort: 3

                 }]

}
