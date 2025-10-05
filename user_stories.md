# User Story Template
**Title:**
_As a [user role], I want [feature/goal], so that [reason]._

**Acceptance Criteria:**
1. [Criteria 1]
2. [Criteria 2]
3. [Criteria 3]

**Priority:** [High/Medium/Low]  
**Story Points:** [Estimated Effort in Points]  
**Notes:**
- [Additional information or edge cases]

---

# Admin User Stories

**Title:** Admin Login  
_As an admin, I want to log into the portal with my username and password so that I can manage the platform securely._  

**Acceptance Criteria:**  
1. Login form accepts valid admin credentials.  
2. Successful login redirects to the Admin Dashboard.  
3. Invalid credentials display an error message.  

**Priority:** High  
**Story Points:** 3  
**Notes:**  
- Authentication handled via Spring Security.  

---

**Title:** Admin Logout  
_As an admin, I want to log out of the portal so that I can protect system access._  

**Acceptance Criteria:**  
1. Logout button is visible on all admin pages.  
2. Logout redirects to the login page.  
3. Session is invalidated on logout.  

**Priority:** High  
**Story Points:** 2  

---

**Title:** Add Doctor  
_As an admin, I want to add new doctors to the portal so that patients can book appointments with them._  

**Acceptance Criteria:**  
1. Admin can input doctor details and save them.  
2. New doctors appear in the doctor list.  
3. Data is stored in the MySQL database.  

**Priority:** High  
**Story Points:** 4  

---

**Title:** Delete Doctor  
_As an admin, I want to delete a doctor’s profile from the portal so that outdated or inactive profiles are removed._  

**Acceptance Criteria:**  
1. Admin can select and delete a doctor.  
2. Confirmation is required before deletion.  
3. Deleted doctor no longer appears in the system.  

**Priority:** Medium  
**Story Points:** 3  

---

**Title:** Run MySQL Report  
_As an admin, I want to run a stored procedure in MySQL CLI to get the number of appointments per month so that I can track usage statistics._  

**Acceptance Criteria:**  
1. Admin can execute the stored procedure from CLI.  
2. Results show appointment counts by month.  
3. Procedure can be reused or scheduled later.  

**Priority:** Medium  
**Story Points:** 2  

---

# Patient User Stories

**Title:** View Doctors Without Login  
_As a patient, I want to view a list of doctors without logging in so that I can explore available options before registering._  

**Acceptance Criteria:**  
1. Doctor list page is accessible publicly.  
2. Displays doctor name, specialization, and availability.  
3. Option to sign up appears below the list.  

**Priority:** High  
**Story Points:** 2  

---

**Title:** Patient Registration  
_As a patient, I want to sign up using my email and password so that I can book appointments._  

**Acceptance Criteria:**  
1. Registration form validates required fields.  
2. On success, patient is saved in the database.  
3. Confirmation message is shown.  

**Priority:** High  
**Story Points:** 3  

---

**Title:** Patient Login  
_As a patient, I want to log into the portal so that I can manage my bookings._  

**Acceptance Criteria:**  
1. Login form accepts valid patient credentials.  
2. Redirect to Patient Dashboard upon success.  
3. Invalid credentials show an error message.  

**Priority:** High  
**Story Points:** 3  

---

**Title:** Book Appointment  
_As a patient, I want to book an hour-long appointment with a doctor so that I can receive consultation._  

**Acceptance Criteria:**  
1. Only available slots can be booked.  
2. Appointment duration defaults to one hour.  
3. Confirmation email or screen message shown.  

**Priority:** High  
**Story Points:** 5  

---

**Title:** View Upcoming Appointments  
_As a patient, I want to view my upcoming appointments so that I can prepare accordingly._  

**Acceptance Criteria:**  
1. Dashboard lists all future appointments.  
2. Shows date, doctor, and time.  
3. Allows cancellation of future appointments.  

**Priority:** Medium  
**Story Points:** 3  

---

# Doctor User Stories

**Title:** Doctor Login  
_As a doctor, I want to log into the portal so that I can manage my appointments._  

**Acceptance Criteria:**  
1. Doctor credentials validated through login form.  
2. Redirects to Doctor Dashboard.  
3. Displays personalized welcome message.  

**Priority:** High  
**Story Points:** 3  

---

**Title:** Doctor Logout  
_As a doctor, I want to log out of the portal so that I can protect my data._  

**Acceptance Criteria:**  
1. Logout link visible on all pages.  
2. Session invalidated and redirected to login.  
3. No access to protected pages after logout.  

**Priority:** High  
**Story Points:** 2  

---

**Title:** View Appointment Calendar  
_As a doctor, I want to view my appointment calendar so that I can stay organized._  

**Acceptance Criteria:**  
1. Displays daily/weekly view of scheduled appointments.  
2. Shows patient name, time, and duration.  
3. Updates dynamically when appointments are added or canceled.  

**Priority:** High  
**Story Points:** 4  

---

**Title:** Mark Unavailability  
_As a doctor, I want to mark my unavailability so that patients can only book available slots._  

**Acceptance Criteria:**  
1. Doctor can select unavailable dates/times.  
2. Unavailable slots are hidden from patient booking.  
3. Updates reflected in database immediately.  

**Priority:** Medium  
**Story Points:** 3  

---

**Title:** Update Profile Information  
_As a doctor, I want to update my specialization and contact information so that patients have up-to-date details._  

**Acceptance Criteria:**  
1. Doctor can modify specialization, phone, and email.  
2. Changes saved to MySQL database.  
3. Confirmation shown after update.  

**Priority:** Medium  
**Story Points:** 2  

---

**Title:** View Patient Details  
_As a doctor, I want to view patient details for my upcoming appointments so that I can prepare beforehand._  

**Acceptance Criteria:**  
1. Doctor can click on appointment to view patient info.  
2. Shows patient’s name, reason for visit, and medical history summary.  
3. Accessible only to the assigned doctor.  

**Priority:** High  
**Story Points:** 4  
