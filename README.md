# Labor Theory of Property (LTP)
The labor theory of property is described by economist and computer scientist Dr. David Ellerman. This project is an implementation of this economic model on a blockchain computer called RChain using a language called Rholang. See: http://www.ellerman.org/on-property-theory/

The project is funded by the RChain bountry program. See: https://github.com/rchain/bounties/issues/1006

## Data Model and Capabilities

![Lifecycle of a Property Right](/glenbraun/LTP/Lifecycle.png)

From: David Ellerman, [On Property Theory](http://www.ellerman.org/wp-content/uploads/2014/11/OnPropertyTheory-Reprint-singles.pdf), Copyright: David Ellerman, 2018

### Birth of Property Rights
The POC will model the birth of a property right as an immutable data object called an Activity-Record.
		
    Activity-Record data object
        UID
        Claims of Human Activity
        Relevant Timespan
		
Where:

Attribute | Mutablility | Description
--------- | ----------- | -----------
UID	      | Immutable   | A unique identifier of the Activity-Record
Claims of Human Activity | Immutable | A list of strings with no specified structure. Future enhancements can define structured expressions of claims.
Relevant Timespan | Immutable | A lower and upper bound of when the human activity took place. Can be very rough dates and does not imply that all of the time was spent on the activity, only that there's no claim to activity outside this timespan related to this record.

Some characteristics of Activity-Records:
* Activity-Records cannot be transferred. Ownership always remains with the person who performed the activity.
* Activity-Records are private information by default but can be shared by the choice of the owner and under terms which the owner agrees.
		
Open Issues:
> Does an unforgeable name serve as a unique identifier and holding a reference to that name holds a reference to the data object? 

> In which case, what does sending or receiving on that name mean? Should it not be possible to send and receive on the name? The name is only passed as an identifier?

> And, is the actual data of the object stored someplace else? Only a reference to it, in the form of the existans of a name (registered) establishes its existance? That is, registring `bundle0(n)` would establish a URI which is the off-chain identifier for the on-chain thing which n is the identifier.

> How private is the URI returned from either of the name registry features, either insertArbitrary or insertSigned. If one were to deploy rholang code which did a lookup using the URI wouldn't that make the URI public? This means that anyone can get a reference to the name. What is returned from the lookup? Is it really any term? Or specifically a name? I think it is a term.
		
> What capability does insertSigned give you that insertArbitrary does not? 
		
### Producer
A producer is an organization of one or more people who pool their efforts to produce something of value which will be sold on the market. A compensation-agreement captures the terms of compensation for the right of the organization to make use of something brought into the organization. Ownership of a producer firm is defined by the state of its compensation-agreements.
		
In the Rholang implementation, a Compensation-Agreement is modeled as both an immutable data object and the capabilities related to it. 
		
    Compensation-Agreement
        UID
        Activity-Records
        Terms
        Acceptance Date
        Contributor-Signature
        Producer-Signature

Where:

Attribute | Mutablility | Description
--------- | ----------- | -----------
UID	      | Immutable   | A unique identifier for the agreement.
Activity-Records | Immutable | A set of activity records used to justify compensation within a producer organization.
Terms | Immutable | A structured data object specifying the purchase price, interest rate, and maximum compensation amount.
Acceptance Date | Immutable | The date the agreement was accept by both parties.
Contributor-Signature | Immutable | Formal acceptance of the agreement by the contributor.
Producer-Signature | Immutable | Formal acceptance of the agreement by the producer organization.
			
#### Capabilities
Capability | Description
---------- | -----------
Make Payment | Transfer funds to the owner of the agreement.
Make Refund  | Perhaps the funds need to flow in the other direction. (Likely will only implement Make Payment)

#### Implied Capabilities
Implied Capability | Description
------------------ | -----------
Get State | Determine the state of the agreement. Is the agreement fully compensated or not?
Tally Compensation | To count the total of all contributions.
List Payments | To gather a history of all payments made to the owner.


Some characteristics of Compensation-Agreements
* The compensation agreement is between a contributor (owner of the activity-records) and the producer organization.
* All of the activity-records must be held by the same person.
		
Open questions:
> What is it each party is signing?
		
### Market
The market provides a system of transferring rights of ownership of the outputs of a produce to a consumer. 
		
    Revenue-Endpoint
		
### Customer
Transfers funds from customer to producer.
	
    Purchase-Agreement
		
### Death of Property Rights
The property rights are dissolved.

    Proof-of-Purchase
		
		
