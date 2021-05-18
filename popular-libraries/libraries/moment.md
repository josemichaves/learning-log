# Moment

![](../../.gitbook/assets/image%20%2817%29.png)

Moment is a library that allows us to parse, validate, manipulate, and display dates and times using a clean and concise API, it can be run from the server and also from NodeJs.

## The basic unit

The basic unit of Moment Js is the `moment()` object, if we call this object alone it will give us the moment of today.

## What is a moment?

A moment is the unit in which moment js represent the data if we call `moment()` we'll get this

```typescript
Moment {
    _isAMomentObject: true,
    _isUTC: false,
    _pf: Object,
    _locale: Locale,
    _d: Wed May 19 2021 00: 48: 19 GMT + 0200(Central European Summer Time)…
}
_isAMomentObject: true
_isUTC: false
_pf: Object
_locale: Locale
_d: Wed May 19 2021 00: 48: 19 GMT + 0200(Central European Summer Time)
_isValid: true
add: ƒ() {}
calendar: ƒ calendar$1() {}
clone: ƒ clone() {}
diff: ƒ diff() {}
endOf: ƒ endOf() {}
format: ƒ format() {}
from: ƒ from() {}
fromNow: ƒ fromNow() {}
to: ƒ to() {}
toNow: ƒ toNow() {}
get: ƒ stringGet() {}
invalidAt: ƒ invalidAt() {}
isAfter: ƒ isAfter() {}
isBefore: ƒ isBefore() {}
isBetween: ƒ isBetween() {}
isSame: ƒ isSame() {}
isSameOrAfter: ƒ isSameOrAfter() {}
isSameOrBefore: ƒ isSameOrBefore() {}
isValid: ƒ isValid$2() {}
lang: ƒ() {}
locale: ƒ locale() {}
localeData: ƒ localeData() {}
max: ƒ() {}
min: ƒ() {}
parsingFlags: ƒ parsingFlags() {}
set: ƒ stringSet() {}
startOf: ƒ startOf() {}
subtract: ƒ() {}
toArray: ƒ toArray() {}
toObject: ƒ toObject() {}
toDate: ƒ toDate() {}
toISOString: ƒ toISOString() {}
inspect: ƒ inspect() {}
toJSON: ƒ toJSON() {}
toString: ƒ toString() {}
unix: ƒ unix() {}
valueOf: ƒ valueOf() {}
creationData: ƒ creationData() {}
eraName: ƒ getEraName() {}
eraNarrow: ƒ getEraNarrow() {}
eraAbbr: ƒ getEraAbbr() {}
eraYear: ƒ getEraYear() {}
year: ƒ() {}
isLeapYear: ƒ getIsLeapYear() {}
weekYear: ƒ getSetWeekYear() {}
isoWeekYear: ƒ getSetISOWeekYear() {}
quarters: ƒ getSetQuarter() {}
quarter: ƒ getSetQuarter() {}
month: ƒ getSetMonth() {}
daysInMonth: ƒ getDaysInMonth() {}
weeks: ƒ getSetWeek() {}
week: ƒ getSetWeek() {}
isoWeeks: ƒ getSetISOWeek() {}
isoWeek: ƒ getSetISOWeek() {}
weeksInYear: ƒ getWeeksInYear() {}
weeksInWeekYear: ƒ getWeeksInWeekYear() {}
isoWeeksInYear: ƒ getISOWeeksInYear() {}
isoWeeksInISOWeekYear: ƒ getISOWeeksInISOWeekYear() {}
date: ƒ() {}
days: ƒ getSetDayOfWeek() {}
day: ƒ getSetDayOfWeek() {}
weekday: ƒ getSetLocaleDayOfWeek() {}
isoWeekday: ƒ getSetISODayOfWeek() {}
dayOfYear: ƒ getSetDayOfYear() {}
hours: ƒ() {}
hour: ƒ() {}
minutes: ƒ() {}
minute: ƒ() {}
seconds: ƒ() {}
second: ƒ() {}
milliseconds: ƒ() {}
millisecond: ƒ() {}
utcOffset: ƒ getSetOffset() {}
utc: ƒ setOffsetToUTC() {}
local: ƒ setOffsetToLocal() {}
parseZone: ƒ setOffsetToParsedOffset() {}
hasAlignedHourOffset: ƒ hasAlignedHourOffset() {}
isDST: ƒ isDaylightSavingTime() {}
isLocal: ƒ isLocal() {}
isUtcOffset: ƒ isUtcOffset() {}
isUtc: ƒ isUtc() {}
isUTC: ƒ isUtc() {}
zoneAbbr: ƒ getZoneAbbr() {}
zoneName: ƒ getZoneName() {}
dates: ƒ() {}
months: ƒ() {}
years: ƒ() {}
zone: ƒ() {}
isDSTShifted: ƒ() {} <
    constructor >: "Moment"
```

As we can see the moment object contains a lot of info, but we can filter this data.

## Date formatting

If we call `moment().format('DD-MM-YYYY')` we we'll obtain "19-05-2021" \(the current day\) or we can also call `moment().format('X')` that we'll give us "1621378555" the current timestamp, we have a lot of ways to obtain data and formatting it.

## Date validation

Moment is also useful to check if a date is valid we can use `moment(theDateToCheck).isValid()`, and will return a boolean.

## Manipulating dates

With moment we can even alter the dates, we can subtract and add days, weeks, minutes or whatever we need to a date

```typescript
moment().add(5, 'days').format('DD-MM-YYYY')
// 24-05-2021

moment().subtract(5, 'days').format('DD-MM-YYYY')
//14-05-2021
```

Calculating the difference between dates is also possible

```typescript
const dateStart = moment("05-05-2021", 'DD-MM-YYYY');
const dateEnd = moment("30-05-2021", 'DD-MM-YYYY');
console.log(`Difference is ${dateEnd.diff(dateStart, "days")} days.`)

//Difference is 25 days.
```

Also check if a date is the same, before, after, etc of another date

```typescript
const dateStart = moment("05-05-2021", 'DD-MM-YYYY');
const dateEnd = moment("30-05-2021", 'DD-MM-YYYY');
console.log(dateEnd.isBefore(dateStart));
console.log(dateEnd.isAfter(dateStart))
  
//False
//True
```

## Timezones and locale

We have a lot of timezones in the world, the "default" is the UTC, using UTC is easy.

* Without `moment-timezone`

  ```typescript
  const momentDate = moment().utc()
  ```

* With `moment-timezone`

  ```typescript
  import * as moment from "moment-timezone"

  moment.tz.setDefault('Etc-UTC')

  //miércoles 19-mayo-2021
  ```

  * Moment-timezone is a library from MomentJs also that allows us to easily deal with the timezone.

Finally we can specify our local language to get the format accordingly

```typescript
moment.locale("es");

console.log(moment().format("dddd DD-MMMM-YYYY"));

//miércoles 19-mayo-2021
```



