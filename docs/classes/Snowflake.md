[**@selize/utils**](../README.md)

***

[@selize/utils](../globals.md) / Snowflake

# Class: Snowflake

Defined in: [uuid/snowflake.ts:29](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L29)

Twitter's distributed auto-increment ID snowflake algorithm([https://github.com/twitter/snowflake](https://github.com/twitter/snowflake)),

default start time: 

2025-01-01 00:00:00Z / 1735660800000

## Example

```ts
import { Snowflake } from '@selize/utils';

const sf = new Snowflake({workId: 1, datacenterId: 1, epoch: 1735660800000})
const uuid = sf.nextId()
console.log('Generated UUID:', id.toString());
// Generated UUID: 69715707826409472n

const parsed = sf.parseId(id);
console.log('Parsed ID:', parsed);
// Parsed ID:
// {
//   "timestamp": 1752282320001,
//   "datacenterId": 1,
//   "workerId": 1,
//   "sequence": 0
// }
```

## See

https://utils.selize.snroe.com/classes/uuid_snowflake.Snowflake.html

## Constructors

### Constructor

> **new Snowflake**(`options`): `Snowflake`

Defined in: [uuid/snowflake.ts:99](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L99)

Constructor

#### Parameters

##### options

Configuration Item

###### datacenterId?

`number`

Data Center ID

###### epoch?

`number`

default start time: 2025-01-01 00:00:00Z / 1735660800000

###### workerId?

`number`

Work Node ID

#### Returns

`Snowflake`

## Properties

### datacenterId

> `private` **datacenterId**: `number` = `1`

Defined in: [uuid/snowflake.ts:56](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L56)

Data center ID (0~31)

***

### datacenterIdBits

> `private` `readonly` **datacenterIdBits**: `number` = `5`

Defined in: [uuid/snowflake.ts:39](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L39)

The number of bits occupied by the data identifier ID

***

### datacenterIdShift

> `private` `readonly` **datacenterIdShift**: `number`

Defined in: [uuid/snowflake.ts:82](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L82)

The data identification ID is shifted left by 17 bits (12+5).

***

### epoch

> `private` **epoch**: `number` = `1735660800000`

Defined in: [uuid/snowflake.ts:48](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L48)

Start time cut-off (2025-01-01 00:00:00)

***

### lastTimestamp

> `private` **lastTimestamp**: `number` = `-1`

Defined in: [uuid/snowflake.ts:64](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L64)

The timestamp of the last generated ID

***

### MAX\_UINT64

> `private` `readonly` **MAX\_UINT64**: `18446744073709551615n` = `0xFFFFFFFFFFFFFFFFn`

Defined in: [uuid/snowflake.ts:31](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L31)

***

### maxDatacenterId

> `private` `readonly` **maxDatacenterId**: `number`

Defined in: [uuid/snowflake.ts:73](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L73)

The maximum supported data identifier ID

***

### maxWorkerId

> `private` `readonly` **maxWorkerId**: `number`

Defined in: [uuid/snowflake.ts:69](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L69)

Maximum supported machine ID

***

### sequence

> `private` **sequence**: `number` = `0`

Defined in: [uuid/snowflake.ts:60](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L60)

Millisecond sequence (0~4095)

***

### sequenceBits

> `private` `readonly` **sequenceBits**: `number` = `12`

Defined in: [uuid/snowflake.ts:43](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L43)

The number of digits occupied by the sequence in the ID

***

### sequenceMask

> `private` `readonly` **sequenceMask**: `number`

Defined in: [uuid/snowflake.ts:90](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L90)

Generate a mask for the sequence, here it is 4095 (0b111111111111=0xfff=4095)

***

### timestampLeftShift

> `private` `readonly` **timestampLeftShift**: `number`

Defined in: [uuid/snowflake.ts:86](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L86)

The time is shifted left by 22 bits (5+5+12)

***

### totalBits

> `private` `readonly` **totalBits**: `BigInt`

Defined in: [uuid/snowflake.ts:30](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L30)

***

### workerId

> `private` **workerId**: `number` = `1`

Defined in: [uuid/snowflake.ts:52](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L52)

Work machine ID (0~31)

***

### workerIdBits

> `private` `readonly` **workerIdBits**: `number` = `5`

Defined in: [uuid/snowflake.ts:35](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L35)

The number of bits occupied by the machine ID

***

### workerIdShift

> `private` `readonly` **workerIdShift**: `number`

Defined in: [uuid/snowflake.ts:78](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L78)

The machine ID shifts left by 12 bits.

## Methods

### nextId()

> **nextId**(): `bigint`

Defined in: [uuid/snowflake.ts:139](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L139)

Generate the next ID

#### Returns

`bigint`

64-bit ID

***

### parseId()

> **parseId**(`id`): `object`

Defined in: [uuid/snowflake.ts:188](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L188)

Analyze ID

#### Parameters

##### id

`bigint`

64-bit ID

#### Returns

`object`

Analysis results with:
- `timestamp`: Milliseconds since epoch
- `datacenterId`: Datacenter ID part of the Snowflake ID
- `workerId`: Worker node ID part of the Snowflake ID
- `sequence`: Sequence number for IDs generated in the same millisecond

##### datacenterId

> **datacenterId**: `number`

##### sequence

> **sequence**: `number`

##### timestamp

> **timestamp**: `number`

##### workerId

> **workerId**: `number`

#### Example

```ts
const uuid = (69715707826409472n).toBigInt();
const parsed = snowflake.parseId(uuid);

console.log('Parsed ID:', parsed);
// Parsed ID:
// {
//   "timestamp": 1752282320001,
//   "datacenterId": 1,
//   "workerId": 1,
//   "sequence": 0
// }
```

***

### tilNextMillis()

> `private` **tilNextMillis**(`lastTimestamp`): `number`

Defined in: [uuid/snowflake.ts:127](https://github.com/snroe/snet-utils/blob/main/src/modules/uuid/snowflake.ts#L127)

Block until the next millisecond,
until a new timestamp is obtained.

#### Parameters

##### lastTimestamp

`number`

The timestamp of the last generated ID

#### Returns

`number`

Current timestamp
