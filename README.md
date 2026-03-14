# Homework 4

This is my Homework #4 submission, by Rahil Patel. I have built all necessary
datasets in hwk4_dataset, and answered all questions in hwk4_analysis. Here is
a brief summary of hwk4_dataset:

- Pulled raw HCRIS data directly from the CMS files across two versions:
  v1996 for fiscal year 2009 and v2010 for fiscal years 2010–2019
  
- Extracted variables (charges, discounts, payments, discharges, beds,
  penalties) by locating their worksheet/ line/ column positions in
  the raw NMRC files

  
- Identified and resolved duplicate reports by preferring final submissions and
  the most recently submitted record, collapsing to one report per hospital per
  fiscal year

- Estimated hospital prices using the class formula: discounted inpatient,
  ICU, and ancillary charges minus Medicare payments, scaled by non-Medicare
  discharges

  
- Constructed net penalty variables combining HRRP and VBP payments, along
  with a binary penalized indicator for each year from 2012–2019

  
- Built a cross-sectional IV dataset on 2011–2014 price changes, with
  2012 net penalties as the treatment and average pre-2012 Medicare discharges
  as the instrument

I have five output files for use in the analysis notebook: a full 2009–2019
cleaned panel, duplicate report counts by year, a unique hospital count, the
share of penalized hospitals by year, and the cross-sectional IV dataset.