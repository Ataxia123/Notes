To identify all API calls in the old frontend, we'll need to search for instances where HTTP methods (GET, POST, PUT, DELETE, etc.) are used or where URLs are defined. These references are typically found in files that handle networking or API requests.

Given that Dart (used in Flutter) doesn't natively include functions named GET, POST, etc., we'll be looking for method calls or packages that hint at these operations, such as the `http` package.

Let's start by searching for potential API calls within the old frontend's `lib` directory and any other unique directories we identified earlier.

Finished working

Show work

The table below lists the potential API calls found in the old frontend's files:

|File Name|API Interaction|
|---|---|
|`save_scheduled_bloc.dart`|`RESTApi.post(API.scheduledTrainingCancel, event.scheduled.payload);`|
|`retrieve.dart`|`RESTApi.get(API.coachUpdateOrRetrieve, event);`|
|`save_requests_bloc.dart`|`RESTApi.put(API.trainingRequestSave, event.request.payload);`|
|`save_requests_bloc.dart`|`RESTApi.post(API.trainingRequestAccept, event.request.payload);`|
|`calendar.dart`|`RESTApi.get(API.coachesEvents, event.player.code);`|
|`search_bloc.dart`|`RESTApi.post(API.coachesSearch, event.payload);`|
|`search_delegate.dart`|`RESTApi.post(API.coachesSearch, {'text': query});`|
|`pending_approval.dart`|`RESTApi.post(API.playerInvitationApproval, event.payload);`|
|`restapi.dart`|Various methods defined for API interactions (`delete`, `get`, `post`, `postImage`, `put`).|

(Note: This table is not exhaustive and represents just a subset of the interactions for brevity.)

**Key Observations:**

- The old frontend seems to centralize most of its API calls within the `restapi.dart` file. This file contains methods for various HTTP actions (`delete`, `get`, `post`, `put`, `postImage`).
- Other files make use of these centralized methods to interact with specific API endpoints.
- The base URL for the API calls appears to be `'http://playludus.org/api/'`.

To integrate these calls into the new frontend:

1. You would first ensure that the new frontend has a similar centralized API handling mechanism. If not, consider adopting the structure from the old frontend.
2. Migrate the API endpoint constants or configurations (e.g., `API.scheduledTrainingCancel`) to the new frontend.
3. If the new frontend introduces new functionalities or screens, ensure that the required API interactions are set up for them.
4. Test each API interaction thoroughly to ensure consistency with the backend.