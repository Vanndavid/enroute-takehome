# Take-Home Test: Vehicle Inspection System

A full-stack vehicle inspection management system using React + TypeScript (frontend) and Express + TypeScript (backend).

**Recommended Time: around 2 hours** — You may take as long as you need, but please don't overthink it.

---

## Backend Tasks (`/backend`)

### Task 1: Implement `createCheck` controller

The `POST /checks` endpoint controller is not implemented. You need to:

1. Validate request body using `validateCheckRequest(req.body)`
2. Return 400 with `ErrorResponse` format if validation fails
3. Call `checkService.createCheck()` if validation passes
4. Return 201 with the created check

**Verify:** Remove `.skip` from the test `"should create check and return 201"` in `api.test.ts`

### Task 2: Fix the bug in service function `createCheck`

The `hasIssue` flag is not correctly identifying if an inspection record has an issue. Find and fix the bug.

**Verify:** Remove `.skip` from the test `"should set hasIssue to true when any item fails"` in `api.test.ts`

Run `npm test` — all tests should pass.

### Task 3: Complete `deleteCheck` controller

The `DELETE /checks/:id` endpoint is not completed. It will not process the deletion and will return `501` regardless of the success or failure of the deletion. Complete this controller and related service function if applicable.

---

## Frontend Tasks (`/frontend`)

### Task 1: Fix Form Input

Check the form (of Submit Vehicle Inspection Result) to make sure the fields are accepting valid input and address any other bugs.

### Task 2: Change dropdown selection for checklist items

In the form, instead of a dropdown to select the result for checklist items, change them to checkboxes, radio buttons, or any other input type that you think is suitable.

### Task 3: Add Notes Field

In the form, add a textarea for optional notes:

- Maximum 300 characters
- (Optional) Display character counter (e.g., "45/300")
- Include in API request and reset after submission

### Task 4: Implement Toast Notifications

**File:** `src/CheckForm.tsx`

Show visual feedback using the provided `Toast.tsx` and `useToast.ts`:

- Success toast on successful submission
- Error toast on failure
- (Optional) Show a good error message in toast on failure

### Task 5: (Optional) Implement a way to delete an inspection record

Note that this task is **completely optional** and we do not expect you to finish this. However, if you wish, you can implement a way to delete an inspection record, provided that you have completed the `deleteCheck` controller. We will provide feedback if you choose to complete this task.

---

## Questions

Please answer these briefly:

1. **Authentication:** If we need to add authentication to this system, how would you approach it?

To add authentication, I would implement a user management system with login and registration functionality (or admin-created users). Usernames would be based on email addresses, and passwords would be securely hashed using bcrypt.

Upon successful login, the server would generate a JWT token (with expiration). This token would be used to authenticate API requests between frontend and backend. Protected routes would use middleware to verify the token before allowing access. All actions such as create/delete, will record the user that did it.

I would also consider implementing role-based authorization (e.g., admin vs. standard user) to support future feature expansion.
2. **Improvements:** What other improvements would you implement if this were going to production or if you have more time?

If this system were going to production or if I had more time, I would:

- Add stronger schema-based validation
- Improve centralized error handling
- Implement structured logging and monitoring
- Add rate limiting for API protection
- Add pagination and filtering for listing data
- Dockerize the application for consistent deployment
- Improve UI/UX consistency and accessibility
- Use Axios with API interceptors for standardized error handling
- Refactor the folder structure to follow more standard architectural patterns
3. **Tech Stack Experience:** Do you have experience with PHP, Vue.js, or mobile app development (React Native/Flutter)?

Yes, I have extensive commercial experience with PHP (Laravel) and have built multiple production systems including CRM, HR, and project management platforms. I have also worked with Vue.js in professional environments.
Although I do not have commercial experience with Flutter or React Native, I have experimented with Flutter and am familiar with its development concepts.
You can view my portfolio at: https://vanndavidteng.com

4. **AI / Tools:** What tools/assistants did you use while working on this assignment (e.g., GitHub Copilot, ChatGPT, etc.)? We appreciate AI usage, we're interested in _how_ you use these tools.

For this assignment, I used AI tools (such as ChatGPT/Codex) to assist with implementation. I provided small, focused instructions for each task and reviewed the generated code carefully before integrating it.
All logic was validated by running tests, debugging issues, and ensuring I fully understood each part of the implementation. I treat AI as a productivity tool to accelerate development, but I maintain full ownership of the final solution and decision-making process.

5. **Visa Status:** What visa are you currently on?

I am currently on temporary graduate visa (subclass 485), valid until February 2028, with full unrestricted working rights in Australia.

6. **Languages:** What language(s) do you speak and what's your proficiency level?

English – Professional working proficiency

Khmer – Native proficiency

> **Tip:** You can write your answers directly in this README.md file below each question.

---

## Submission (How to Submit)

1. Create a **public GitHub repository** for this assignment.
2. Push your code with all changes.
3. **Create at least two pull requests (PRs):** one for backend and one for frontend. You may create more (e.g., each task can be an independent PR). You may merge them into the main branch. We can review and may leave comments on your PRs for feedback.
4. Answer questions above.
5. **Please complete and submit within 3 days** unless otherwise discussed.
6. Send the repository link to **admin@enroute-tech.com**.

---

Good luck!
