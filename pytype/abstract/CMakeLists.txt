add_package()

py_library(
  NAME
    abstract
  DEPS
    ._abstract
    .abstract_utils
    .class_mixin
    .function
    .mixin
)

py_library(
  NAME
    _abstract
  SRCS
    __init__.py
    abstract.py
  DEPS
    ._base
    ._instance_base
    ._instances
    ._singletons
    .abstract_utils
    .class_mixin
    .function
    .mixin
    pytype.utils
    pytype.pytd.pytd
    pytype.pytd.codegen.codegen
    pytype.typegraph.cfg_utils
)

py_library(
  NAME
    _base
  SRCS
    _base.py
  DEPS
    .abstract_utils
    pytype.utils
    pytype.pytd.pytd
)

py_library(
  NAME
    _instance_base
  SRCS
    _instance_base.py
  DEPS
    ._base
    .abstract_utils
    .class_mixin
    .function
    pytype.utils
)

py_library(
  NAME
    _instances
  SRCS
    _instances.py
  DEPS
    ._base
    ._instance_base
    .abstract_utils
    .function
    .mixin
    pytype.pytd.pytd
    pytype.typegraph.cfg
    pytype.typegraph.cfg_utils
)

py_library(
  NAME
    _singletons
  SRCS
    _singletons.py
  DEPS
    ._base
    pytype.utils
    pytype.pytd.pytd
    pytype.typegraph.cfg
)

py_library(
  NAME
    abstract_utils
  SRCS
    abstract_utils.py
  DEPS
    pytype.utils
    pytype.pyc.pyc
    pytype.typegraph.cfg
    pytype.typegraph.cfg_utils
)

py_library(
  NAME
    class_mixin
  SRCS
    class_mixin.py
  DEPS
    .abstract_utils
    .function
    .mixin
    pytype.utils
    pytype.pytd.pytd
)

py_library(
  NAME
    function
  SRCS
    function.py
  DEPS
    .abstract_utils
    pytype.utils
    pytype.pytd.pytd
)

py_library(
  NAME
    mixin
  SRCS
    mixin.py
  DEPS
    .abstract_utils
    .function
    pytype.typegraph.cfg
)

py_test(
  NAME
    abstract_test
  SRCS
    abstract_test.py
  DEPS
    ._abstract
    .abstract_utils
    .function
    pytype.libvm
    pytype.pytd.pytd
    pytype.tests.test_base
    pytype.typegraph.cfg
)

py_test(
  NAME
    abstract_utils_test
  SRCS
    abstract_utils_test.py
  DEPS
    .abstract_utils
    pytype.libvm
    pytype.tests.test_base
)

py_test(
  NAME
    mixin_test
  SRCS
    mixin_test.py
  DEPS
    .mixin
)
