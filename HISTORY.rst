Changelog
---------

0.5.2 (2014-02-10)
++++++++++++++++++

* Enable custom field validation via the ``validate`` parameter.
* Add ``utils.from_rfc`` for parsing RFC datestring to Python datetime object.

0.5.1 (2014-02-02)
++++++++++++++++++

* Avoid unnecessary attribute access in ``utils.to_marshallable_type`` for improved performance.
* Fix RFC822 formatting for localized datetimes.

0.5.0 (2013-12-29)
++++++++++++++++++

* Can customize validation error messages by passing the ``error`` parameter to a field.
* *Backwards-incompatible*: Rename ``fields.NumberField`` -> ``fields.Number``.
* Add ``fields.Select``. Thanks @ecarreras.
* Support nesting a Serializer within itself by passing ``"self"`` into ``fields.Nested`` (only up to depth=1).
* *Backwards-incompatible*: No implicit serializing of collections. Must set ``many=True`` if serializing to a list. This ensures that marshmallow handles singular objects correctly, even if they are iterable.
* If Nested field ``only`` parameter is a field name, only return a single value for the nested object (instead of a dict) or a flat list of values.
* Improved performance and stability.

0.4.1 (2013-12-01)
++++++++++++++++++

* An object's ``__marshallable__`` method, if defined, takes precedence over ``__getitem__``.
* Generator expressions can be passed to a serializer.
* Better support for serializing list-like collections (e.g. ORM querysets).
* Other minor bugfixes.

0.4.0 (2013-11-24)
++++++++++++++++++

* Add ``additional`` `clas Meta` option.
* Add ``dateformat`` `class Meta` option.
* Support for serializing UUID, date, time, and timedelta objects.
* Remove ``Serializer.to_data`` method. Just use ``Serialize.data`` property.
* String field defaults to empty string instead of ``None``.
* *Backwards-incompatible*: ``isoformat`` and ``rfcformat`` functions moved to utils.py.
* *Backwards-incompatible*: Validation functions moved to validate.py.
* *Backwards-incompatible*: Remove types.py.
* Reorder parameters to ``DateTime`` field (first parameter is dateformat).
* Ensure that ``to_json`` returns bytestrings.
* Fix bug with including an object property in ``fields`` Meta option.
* Fix bug with passing ``None`` to a serializer.

0.3.1 (2013-11-16)
++++++++++++++++++

* Fix bug with serializing dictionaries.
* Fix error raised when serializing empty list.
* Add ``only`` and ``exclude`` parameters to Serializer constructor.
* Add ``strict`` parameter and option: causes Serializer to raise an error if invalid data are passed in, rather than storing errors.
* Updated Flask + SQLA example in docs.

0.3.0 (2013-11-14)
++++++++++++++++++

* Declaring Serializers just got easier. The *class Meta* paradigm allows you to specify fields more concisely. Can specify ``fields`` and ``exclude`` options.
* Allow date formats to be changed by passing ``format`` parameter to ``DateTime`` field constructor. Can either be ``"rfc"`` (default), ``"iso"``, or a date format string.
* More useful error message when declaring fields as classes (instead of an instance, which is the correct usage).
* Rename MarshallingException -> MarshallingError.
* Rename marshmallow.core -> marshmallow.serializer.

0.2.1 (2013-11-12)
++++++++++++++++++

* Allow prefixing field names.
* Fix storing errors on Nested Serializers.
* Python 2.6 support.

0.2.0 (2013-11-11)
++++++++++++++++++

* Field-level validation.
* Add ``fields.Method``.
* Add ``fields.Function``.
* Allow binding of extra data to a serialized object by passing the ``extra`` param when initializing a ``Serializer``.
* Add ``relative`` paramater to ``fields.Url`` that allows for relative URLs.

0.1.0 (2013-11-10)
++++++++++++++++++

* First release.
