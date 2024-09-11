# TikTok Clone NextJs 13 / (tiktok-clone-nextjs)

### Learn how to build this!

See complete tutorial on https://www.youtube.com/watch?v=7zLyVzItZlQ)

## App Setup (localhost)

Create project from scratch:
```
nox create-next-app@latest tiktok-clone-nextjs
TypeScript: Yes
ESLint: No
Tailwind CSS: Yes
src/ directory: No
App Router: Yes
Import Alias: No
```

or

Checkout from git repository:
```
git clone https://github.com/John-Weeks-Dev/tiktok-clone-nextjs.git

cp .env.example .env
```
You'll have to set up an AppWrite account, and then add all of the details into your `.env` file.

`.env` file must contain the following:
```
NEXT_PUBLIC_APPWRITE_URL='https://cloud.appwrite.io/v1'
NEXT_PUBLIC_ENDPOINT=''
NEXT_PUBLIC_DATABASE_ID=''

NEXT_PUBLIC_COLLECTION_ID_PROFILE=''
NEXT_PUBLIC_COLLECTION_ID_POST=''
NEXT_PUBLIC_COLLECTION_ID_LIKE=''
NEXT_PUBLIC_COLLECTION_ID_COMMENT=''

NEXT_PUBLIC_BUCKET_NAME=""
NEXT_PUBLIC_BUCKET_ID=''
NEXT_PUBLIC_PLACEHOLDER_DEAFULT_IMAGE_ID=''
```

## AppWrite Schema

### Database Name: tiktok-clone

### Profile Collection:
| Key | Type |
| --- | --- |
| `Document ID` | String |
| `image` | String |
| `bio` | String |
| `user_id` | String |
| `name` | String |

Profile Indexes:
| KEY           | TYPE          | ATTRIBUTE     | ASC/DESC      |
| ------------- | ------------- | ------------- | ------------- |
| user_id       | key           | user_id       | asc           |
| name          | fulltext      | name          | asc           |

Profile Settings (Update Permissions):
| Add Role      | PERMISSIONS   |
| ------------- | ------------- |
| All guests    | Read          |
| All users     | Create, Read, Update, Delete |

### Post Collection:
| Key | Type |
| --- | --- |
| `Document ID` | String |
| `user_id` | String |
| `video_url` | String |
| `text` | String |
| `created_at` | String |
    
Post Indexes:
| KEY           | TYPE          | ATTRIBUTE     | ASC/DESC      |
| ------------- | ------------- | ------------- | ------------- |
| user_id       | key           | user_id       | asc           |

Profile Settings (Update Permissions):
| Add Role      | PERMISSIONS   |
| ------------- | ------------- |
| All guests    | Read          |
| All users     | Create, Read, Update, Delete |

### Like Collection:
| Key | Type |
| --- | --- |
| `Document ID` | String |
| `user_id` | String |
| `post_id` | String |

Like Indexes: 
| KEY           | TYPE          | ATTRIBUTE     | ASC/DESC      |
| ------------- | ------------- | ------------- | ------------- |
| user_id       | key           | user_id       | asc           |
| id            | unique        | id            | asc           |
| post_id       | key           | post_id       | asc           |

Like Settings (Update Permissions):
| Add Role      | PERMISSIONS   |
| ------------- | ------------- |
| All guests    | Read          |
| All users     | Create, Read, Update, Delete |

### Comment Collection:
| Key | Type |
| --- | --- |
| `Document ID` | String |
| `user_id` | String |
| `post_id` | String |
| `text` | String |
| `created_at` | String |
    
Comment Indexes:
| KEY           | TYPE          | ATTRIBUTE     | ASC/DESC      |
| ------------- | ------------- | ------------- | ------------- |
| post_id       | key           | post_id       | asc           |

Comment Settings (Update Permissions):
| Add Role      | PERMISSIONS   |
| ------------- | ------------- |
| All guests    | Read          |
| All users     | Create, Read, Update, Delete |


Once you've connected your application to AppWrite. Run the commands.
    
```
npm i

npm run dev
```

