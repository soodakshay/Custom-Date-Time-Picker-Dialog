A Material design back port of Android's CalendarView. The goal is to have a Material look and feel, rather than 100% parity with the platform's implementation.

Usage: 

```DatePickerDialog datePickerDialog = DatePickerDialog.newInstance(new DatePickerDialog.OnDateSetListener() {
 @Override 
      public void onDateSet(DatePickerDialog view, int year, int monthOfYear,int dayOfMonth) {
        Calendar calendar = Calendar.getInstance();
        calendar.set(year, monthOfYear, dayOfMonth);

        mIGenInfoPresenter.onDateSelected(new SimpleDateFormat("dd-MM-yyyy").format(calendar.getTime()));
      }
    }, oldYear, oldMonth, oldDay);
    datePickerDialog.vibrate(true); // Vibration on every view touch
    datePickerDialog.dismissOnPause(false); // dismiss when activity or fragment pause
    datePickerDialog.setVersion(DatePickerDialog.Version.VERSION_2); // marshmallow theme// for Lolipop theme use version 1
    datePickerDialog.setAccentColor(ContextCompat.getColor(context, R.color.colorPrimary)); 
    datePickerDialog.setMaxDate(getMaxDate());
    datePickerDialog.show(fragmentManager,null);
    
    
    /**
   * get max date ex: user must be atleast 17 years old so dont show other dates
   */
  private Calendar getMaxDate() {
    Calendar mCal = Calendar.getInstance();
    int year = mCal.get(Calendar.YEAR) - 17;
    mCal.set(Calendar.YEAR, year);
    return mCal;
  }
  ```
