# Homework 4

This is my Homework #4 submission, by Rahil Patel. I have built all necessary
datasets in hwk4_dataset, and answered all questions in hwk4_analysis. Here is
a brief summary of hwk4_dataset:

- Pulled raw HCRIS data directly from the CMS files across the 2 versions.
  v1996 for fiscal years 2009 and 2010, and v2010 for fiscal years 2011–2019

- Extracted variables (charges, discounts, payments, discharges, beds, and
  penalty adjustments) by locating their exact worksheet, line, and column
  positions in the raw NMRC files

- Identified and resolved duplicate reports by preferring final submissions and
  the most recently submitted record. I collapsed it to one report per hospital per
  fiscal year

- Estimated hospital prices based on the formula we learned in the slides. Discounted
  inpatient, ICU, and ancillary charges minus total Medicare payments, scaled
  by non-Medicare discharges. Negative and infinite prices were dropped

- Kept HRRP and VBP payments as signed values since both programs reduce
  Medicare payments. Net penalty is their signed sum, and the binary penalty
  indicator flags any hospital where that sum falls below zero

- Tracked the share of penalized hospitals annually from 2012–2019

- Built a cross-sectional IV dataset linking 2011 and 2014 prices, 2012 net
  penalties, and pre-2012 averages for Medicare discharges, beds, and Medicaid
  discharges. Medicare discharges are scaled to hundreds to make it easier to
  interpret

I have five output files for use in the analysis notebook: a full 2009–2019
cleaned panel, duplicate report counts by year, a unique hospital count, the
share of penalized hospitals by year, and the cross-sectional IV dataset.