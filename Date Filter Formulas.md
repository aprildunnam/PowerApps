//Date Filter Collection to get This Week, Last Week and Last Pay Period (2 Weeks)
ClearCollect(
    colTimeFilter,
    {
        DisplayName: "This Week",
        StartDate: DateAdd(
            Today(),
            1 - Weekday(
                Today(),
                StartOfWeek.Monday
            ),
            Days
        ),
        EndDate: DateAdd(
            Today(),
            1 - Weekday(
                Today(),
                StartOfWeek.Monday
            ) + 6,
            Days
        )
    },
    {
        DisplayName: "Last Week",
        StartDate: DateAdd(
            Today(),
            -6 - Weekday(
                Today(),
                StartOfWeek.Monday
            ),
            Days
        ),
        EndDate: DateAdd(
            Today(),
            -6 - Weekday(
                Today(),
                StartOfWeek.Monday
            ) + 6,
            Days
        )
    },
    {
        DisplayName: "Last Pay Period",
        StartDate: DateAdd(
            Today(),
            -12 - Weekday(
                Today(),
                StartOfWeek.Monday
            ),
            Days
        ),
        EndDate: DateAdd(
            Today(),
            -12 - Weekday(
                Today(),
                StartOfWeek.Monday
            ) + 12,
            Days
        )
    }
)

//Filter to apply on the Gallery
Sort(
    Filter(
        TimeClockData,
        Date >= ddTimeSelection.Selected.StartDate && Date <= ddTimeSelection.Selected.EndDate
    ),
    Date,
    Descending
)
