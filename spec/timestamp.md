# Timestamp

A timestamp is a column that captures the time at which the inference was made. This is typically the time at which the inference was made in production.

Timestamp columns are prefixed with the category `:timestamp:` in the column name. Timestamps are represented as the following data types:

- **iso_8601**: a string that is an ISO 8601 timestamp
- **milliseconds**: a numeric value that is the Epoch time in milliseconds
- **seconds**: a numeric value that is the Epoch time in seconds

Timestamp columns MUST be singular, meaning that there is only one timestamp column per record. Timestamp columns are typically used to perform time-series analysis.

There are no reserved **specifiers** or **names** for timestamps.

Here are examples of a set of timestamp columns:

<table>
    <thead>
        <tr>
            <th>:timestamp.iso_8601:</th>
            <th>:prediction:str.label:</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>2021-01-01T00:00:00Z</td>
            <td>cat</td>
            </tr>
            <tr>
            <td>2021-01-01T00:00:01Z</td>
            <td>dog</td>
            </tr>
            <tr>
            <td>2021-01-01T00:00:02Z</td>
            <td>cat</td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th>:timestamp.milliseconds:</th>
            <th>:prediction.str.label:</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1689272425546</td>
            <td>cat</td>
            </tr>
            <tr>
            <td>1689272425546</td>
            <td>dog</td>
            </tr>
            <tr>
            <td>1689272425546</td>
            <td>cat</td>
        </tr>
    </tbody>
</table>
