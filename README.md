# natural-orderby for Google Apps Script

This project is unofficial of https://github.com/yobacca/natural-orderby.

Script ID: `1xCU9bCLSlUcp9enPq18yqjzV530lOIM2WqB7OHA7e4Jn2vgvuT5pFyYg`

## Adding the library to your project

Select "Resources" > "Libraries..." in the Google Apps Script editor. Enter the project key (1xCU9bCLSlUcp9enPq18yqjzV530lOIM2WqB7OHA7e4Jn2vgvuT5pFyYg) in the "Find a Library" field, and choose "Select". (If you have copied the library, enter instead the project key of your copy.) Select the highest version number, and choose NaturalSort as the identifier. (Do not turn on Development Mode unless you know what you are doing. The development version may not work.) Press Save. You can now use the Fuse (NaturalSort) library in your code.

## Usage

```js
function naturalsort__test() {
  const { orderBy } = NaturalSort.NaturalOrderby;
  const users = [
    {
      username: 'Bamm-Bamm',
      ip: '192.168.5.2',
      datetime: 'Fri Jun 15 2018 16:48:00 GMT+0200 (CEST)'
    },
    {
      username: 'Wilma',
      ip: '192.168.10.1',
      datetime: '14 Jun 2018 00:00:00 PDT'
    },
    {
      username: 'Dino',
      ip: '192.168.0.2',
      datetime: 'June 15, 2018 14:48:00'
    },
    {
      username: 'Barney',
      ip: '192.168.1.1',
      datetime: 'Thu, 14 Jun 2018 07:00:00 GMT'
    },
    {
      username: 'Pebbles',
      ip: '192.168.1.21',
      datetime: '15 June 2018 14:48 UTC'
    },
    {
      username: 'Hoppy',
      ip: '192.168.5.10',
      datetime: '2018-06-15T14:48:00.000Z'
    },
  ];

  const sortedUsers = orderBy(
    users,
    [v => v.datetime, v => v.ip],
    ['desc', 'asc']
  );
  console.log(sortedUsers)
}

```

Please check out how to use Fuse.js at [natural-orderby](https://yobacca.github.io/natural-orderby)
