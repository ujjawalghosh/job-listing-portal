# Job Portal Deployment Fix - Login Issue

## Status: 🔄 In Progress

## Steps Completed:\n- [x] Diagnosed issue: Frontend uses localhost API in production\n- [x] Fixed frontend API base URL logic\n- [x] Code changes committed & ready to deploy

## Remaining Steps:

### 1. **Set Vercel Environment Variable** (Frontend)
```
Project Settings > Environment Variables > Add:
Name: VITE_API_BASE_URL
Value: https://job-listing-portal-axw0.onrender.com
```
- Add to **Production** environment
- **Redeploy** frontend (or push to trigger)

### 2. **Set Render Environment Variable** (Backend)
```
Dashboard > Your Service > Environment > Add:
Key: PUBLIC_BACKEND_URL
Value: https://job-listing-portal-axw0.onrender.com
```
- Save → triggers redeploy

### 3. **Test Login**
- Visit Vercel frontend URL
- Try login → check Network tab (F12): API calls to Render URL?
- Success: Returns token, redirects to dashboard

### 4. **Verify Image Uploads**
- Profile upload → image loads from Render /uploads/

### 5. **Monitor Logs**
```
Render: Logs tab for backend errors
Vercel: Functions logs for frontend
```

## After Completion
```
npm run build && vercel deploy  # Frontend (optional)
```
**Expected Result**: Login works across deploys! 🚀

**Current Progress**: [Update after each step]
