# slim.reset train without dataset

The `slim.reset` models all need a dataset to train on. The datasets
must first be prepared to create a train/test split.

Training without a dataset argument is an error:

    >>> run("guild run resnet-50:train -y")
    Operation requires the following missing flags:
    <BLANKLINE>
    dataset  Dataset to train with (cifar10, mnist, flowers, custom)
    <BLANKLINE>
    Run the command again with these flags specified as NAME=VAL.
    <exit 1>

Training without a prepared dataset is an error:

    >>> run("guild run resnet-50:train dataset=flowers -y")
    Resolving slim/lib dependency
    ...
    Resolving slim-datasets:flowers dependency
    guild: run failed because a dependency was not met: could not resolve
    'operation:slim-flowers:prepare' in flowers resource: no suitable run
    for slim-flowers:prepare
    <exit 1>