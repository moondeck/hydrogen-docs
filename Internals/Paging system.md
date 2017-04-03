#Paging system

This document contains information about the paging system in Hydrogen

##Page flags
Page flags are:

    PFLAG_GLOBAL - Prevents the page entry in TLB from being updated. Must be enabled in CR4.  
    PFLAG_CACHED - DISABLES caching of the page.
    PFLAG_WRITET - Enables write-through on the page.
    PFLAG_USRSUP - Access to the page. If set, everyone can access the page, if not, its supervisor-only.
    PFLAG_READWR - Enables Read/Write

The "Present" flag is set automatically.
If multiple flags are needed, ORing should be used

###Example usage:

    map_pv(0xDEADBEEF, 0xCAFEBABE, PFLAG_READWR | PFLAG_USRSUP); 
    //maps 0xDEADBEEF virtual to 0xCAFEBABE physical with RW and user access.