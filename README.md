# Labor Theory of Property (LTP)
The labor theory of property is described by economist and computer scientist Dr. David Ellerman. This project is an implementation of this economic model on a blockchain computer called RChain using a language called Rholang. See: http://www.ellerman.org/on-property-theory/

The project is funded by the RChain bountry program. See: https://github.com/rchain/bounties/issues/1006

## Data Model and Operations

### Labor Property
A Labor Property is a claim of performing some human activity.

_Timeframe_
>A general indication of when the activity occurred. 

_Claims_
>Descriptive claims of human activities. Examples include hours of work, a task, anything that accurately describes the human activity.

### Compensation Agreement
A compensation agreement establishes the terms of sale of a labory property to another entity. 

_Price_
>The agreed purchase price.

_InterestRate_
>Expressed as annual, compounded continuously rate. 

_DateOfPurchase_
>When the compensation agreement begins earning interest.

_MaxAmount_
>Provides an upper bound for compensation.

_AmountCompensated_
>How much has been received in compensation.

_IsFullyCompensated_
>Once fully compensated, no more compensation is received.

### Firm
A company seen as a collection of compensation agreements.

_Name_
>A human readable name for the organization.

_CompensationAgreements_
>Agreements to purchase the properties which form the organization.

_RevenueProcess_
>Distributes revenue to pay the compensation agreements.

_Receipts_
>A history of past payments.

