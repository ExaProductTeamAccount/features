<!-- @format -->

## Upgrade Functionality Documentation

The upgrade functionality in the mobile and app enables users to switch to a new subscription plan while preserving the benefits of their current plan. This documentation provides an overview of the upgrade logic and its implementation details.

### Upgrade Logic:

The logic for the upgrade functionality is as follows:

1. When a user has no remaining days on their current plan:

   - The system changes the user's subscription to the new plan.
   - The user starts afresh with the new subscription, and the subscription period begins immediately.

2. When a user has remaining days on their current plan:
   - The system upgrades the user to the new plan.
   - The remaining days from the current plan are added to the duration of the new plan, extending the user's subscription period.
   - Note: This addition of days applies to subscriptions of shorter durations (e.g., monthly) that are being upgraded to longer durations (e.g., 3 months, 6 months, 12 months). However, for longer-duration subscriptions, the remaining days from the current subscription are deducted from the upgraded plan's length.
   - To calculate the deduction, the system assumes that the user has already been on the new subscription for the number of days equivalent to the remaining days on their current plan.
   - The deduction is made to account for the fact that the new subscription is at a lower cost compared to the current subscription.

### Implementation:

The following steps outline the implementation of the upgrade functionality:

1. **Backend Changes**:

   - Update the backend system to handle subscription plan changes and upgrade requests.
   - Implement the logic for determining the remaining days on the current plan and calculating the extension or deduction for the upgraded plan.
   - Ensure proper validation and error handling for invalid upgrade scenarios.

2. **Frontend Integration**:

   - Modify the mobile and app interfaces to provide users with options to upgrade their subscription plans.
   - Implement the necessary user flows and screens to facilitate the upgrade process.
   - Update the user interface to display information about the current plan, remaining days, and the benefits of the new plan.

3. **Database Updates**:
   - Adapt the database schema to accommodate changes in the subscription plans.
   - Store and retrieve information related to the user's current plan, remaining days, and the upgraded plan.

### Usage:

To utilize the upgrade functionality in the mobile and app, follow these steps:

1. Ensure that the backend system has been updated to support the upgrade logic.
2. Integrate the frontend changes to provide a seamless user experience for plan upgrades.
3. Test the upgrade functionality thoroughly, considering various scenarios, such as no remaining days, different plan durations, and error cases.
4. Deploy the updated mobile and app versions with the upgrade functionality to your production environment.

### Considerations:

When implementing the upgrade functionality, keep the following points in mind:

- Properly communicate the upgrade process and any deductions or extensions to the user to avoid confusion.
- Handle edge cases and potential errors, such as users attempting to upgrade invalid plan combinations or encountering connectivity issues during the upgrade process.
- Monitor and log upgrade transactions to ensure accurate tracking of plan changes and to facilitate troubleshooting if needed.

By following the provided documentation, you can successfully implement the upgrade functionality, allowing users to seamlessly switch to new subscription plans while preserving the benefits they have accumulated from their previous plans.
