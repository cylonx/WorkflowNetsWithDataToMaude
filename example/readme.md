![Alt text](/Img/wfd.png?raw=true "Title")

The example depicts a WFD-net modelling the processing of an application for a student loan

The data elements involved are: D = {a, ad, scs, cr, rn, ld}. 

The data element available when the process starts
is the student application data (*a*) - which includes financial information about
both the student and a co-signer who is required to co-sign the loan;

Transition
*ra* (receive application), reads the application data. After its execution, *rd* (reg-
ister data) and *vcs* (verify co-signer) can execute in parallel. Both transitions
read the application data (*a*). *rd* registers the data and writes an application
document (*ad*), while *vcs* verifies the financial data of the co-signer and writes
a corresponding report (*cr*). After both transitions execute, if predicate *okC(cr)*
is true, transition *cscs* (compute student credit score) executes, otherwise *rja*
(reject application) executes. Predicate *okC(cr)* is true if the co-signer meets cer-
tain conditions (the predicate depends on the co-signer report, *cr*). *cscs* reads
the application document (*ad*), computes the student credit score and writes it in
the data element *scs*. *rja* writes the application document (*ad*) and a rejection
notice for the student (*rn*), deletes the unnecessary data elements (*a*, *cr*) and the
workflow completes. After the execution of *cscs*, if predicate *okData(cr, scs)* is
true, *apprv* (approve loan) executes, otherwise *rj* (reject) executes. Predicate
*okData(cr, scs)* depends on the co-signer report and the student credit score. *rj*
will write a rejection notice for the student (*rn*). *aprv* will write the application
document and a loan document (*ld*). Both tasks will delete the unnecessary data
(*a*, *cr*, *scs*). After *aprv* executes, one of the transition *sld* (sign loan document)
or *rf* (refuse) can execute and the workflow completes. If *sld* executes, the stu-
dent signs the loan document, that will be written. If *rf* executes, the student
refuses to conditions of the loan (*ld* is read).

