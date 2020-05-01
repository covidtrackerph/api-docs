# CovidTrackerPH API Documentation

The graphQL playground can be found here - https://covidtrackerph.github.io/api-docs/.

# Schema

```graphql
type Accumulation {
  accumulator: DateTime!
  value: Int!
}

input AccumulationInput {
  type: Type!
}

type AgeGenderDistribution {
  ageGroup: String
  sex: String
  value: Int
}

type Case {
  caseNo: String!
  age: Int
  ageGroup: String
  dateConfirmed: DateTime
  dateRecovered: DateTime
  dateDied: DateTime
  removalType: String
  dateRemoved: DateTime
  admitted: Boolean
  healthStatus: String
  region: String
  province: String
  city: String
  insertedAt: DateTime!
  updatedAt: DateTime!
}

type CaseStatistic {
  total: Int!
  new: Int!
  dead: Int!
  deadNew: Int!
  recovered: Int!
  recoveredNew: Int!
  admitted: Int!
  admittedNew: Int!
}

scalar DateTime

type Query {
  cases: [Case!]!
  case(caseNo: String!): Case!
  ageGenderDistribution(type: Type!): [AgeGenderDistribution!]!
  accumulation(type: Type!): [Accumulation!]!
  statistics: CaseStatistic!
}

enum Type {
  TOTAL
  ADMITTED
  DIED
  RECOVERED
}

```
