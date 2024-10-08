# DAX Codes

## Key Measures

### Attrition % Measure
```DAX
Attrition % = 
DIVIDE(
    COUNTROWS(FILTER(hr, hr[Attrition] = "Yes")),
    COUNTROWS(hr),
    0
)


Retention % = 
DIVIDE(
    COUNTROWS(FILTER(hr, hr[Attrition] = "No")),
    COUNTROWS(hr),
    0
)
% = 
SWITCH(
    SELECTEDVALUE(Selection[Selection]),
    "Attrition", [Attrition %],
    [Retention %]
)


% Measure = 
VAR RowEntity = SELECTEDVALUE('DR'[Entity])
VAR ColEntity = SELECTEDVALUE('DC'[Entity])
VAR RowDimension = SELECTEDVALUE('DR'[Dimension])
VAR ColDimension = SELECTEDVALUE('DC'[Dimension])

RETURN 
CALCULATE(
    [%],
    FILTER(
        hr,
        (RowDimension = "Department" && hr[Department] = RowEntity) || 
        (RowDimension = "Education" && hr[Education] = RowEntity) ||
        (RowDimension = "Diverse" && hr[Diverse] = RowEntity) ||
        (RowDimension = "Gender" && hr[Gender] = RowEntity) ||
        (RowDimension = "Performance Score" && hr[Performance Score] = RowEntity) ||
        (RowDimension = "POC or POC NA" && hr[POC or POC NA] = RowEntity) ||
        (RowDimension = "Position" && hr[Position] = RowEntity) ||
        (RowDimension = "Race Desc" && hr[Race Desc] = RowEntity) ||
        (RowDimension = "BusinessTravel" && hr[BusinessTravel] = RowEntity) ||
        (RowDimension = "EducationField" && hr[EducationField] = RowEntity) ||
        (RowDimension = "JobRole" && hr[JobRole] = RowEntity) ||
        (RowDimension = "MaritalStatus" && hr[MaritalStatus] = RowEntity)
    ),
    FILTER(
        hr,
        (ColDimension = "Department" && hr[Department] = ColEntity) || 
        (ColDimension = "Education" && hr[Education] = ColEntity) ||
        (ColDimension = "Diverse" && hr[Diverse] = ColEntity) ||
        (ColDimension = "Gender" && hr[Gender] = ColEntity) ||
        (ColDimension = "Performance Score" && hr[Performance Score] = ColEntity) ||
        (ColDimension = "POC or POC NA" && hr[POC or POC NA] = ColEntity) ||
        (ColDimension = "Position" && hr[Position] = ColEntity) ||
        (ColDimension = "Race Desc" && hr[Race Desc] = ColEntity) ||
        (ColDimension = "BusinessTravel" && hr[BusinessTravel] = ColEntity) ||
        (ColDimension = "EducationField" && hr[EducationField] = ColEntity) ||
        (ColDimension = "JobRole" && hr[JobRole] = ColEntity) ||
        (ColDimension = "MaritalStatus" && hr[MaritalStatus] = ColEntity)
    )
)

DC = DR =  
VAR Department = ADDCOLUMNS(VALUES(hr[Department]), "Dimension", "Department")
VAR Education = ADDCOLUMNS(VALUES(hr[Education]), "Dimension", "Education")
VAR Diverse = ADDCOLUMNS(VALUES(hr[Diverse]), "Dimension", "Diverse")
VAR Gender = ADDCOLUMNS(VALUES(hr[Gender]), "Dimension", "Gender")
VAR PerformanceScore = ADDCOLUMNS(VALUES(hr[Performance Score]), "Dimension", "Performance Score")
VAR POC = ADDCOLUMNS(VALUES(hr[POC or POC NA]), "Dimension", "POC or POC NA")
VAR Position = ADDCOLUMNS(VALUES(hr[Position]), "Dimension", "Position")
VAR RaceDesc = ADDCOLUMNS(VALUES(hr[Race Desc]), "Dimension", "Race Desc")
VAR BusinessTravel = ADDCOLUMNS(VALUES(hr[BusinessTravel]), "Dimension", "BusinessTravel")
VAR EducationField = ADDCOLUMNS(VALUES(hr[EducationField]), "Dimension", "EducationField")
VAR JobRole = ADDCOLUMNS(VALUES(hr[JobRole]), "Dimension", "JobRole")
VAR MaritalStatus = ADDCOLUMNS(VALUES(hr[MaritalStatus]), "Dimension", "MaritalStatus")

RETURN 
UNION(
    Department,
    Education,
    Diverse,
    Gender,
    PerformanceScore,
    POC,
    Position,
    RaceDesc,
    BusinessTravel,
    EducationField,
    JobRole,
    MaritalStatus
)
