
You may specify the date parameters using strings or objects. To use strings, specify the date in the form, YYYYMMDD. If you use objects, create a JSON object with the following fields:<br />

<ul>
    <li>year</li>
    <li>month</li>
    <li>day</li>
</ul>
<br />
For example, `'{ "year": 2016, "month": 5, "day": 13}'`.<br />

The date range is inclusive. If you apply conditions or ordering that reference performance metric fields, you must specify a date range.  Only the last date range specified is used if multiple date ranges are specified.
