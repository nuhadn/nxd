# Pediatric Handover System

A comprehensive web-based patient handover management system for pediatric wards.

## Features

- **Patient Management**: Add, edit, and discharge patients
- **Ward Organization**: Supports multiple ward types (PW, GW, SW, PVT, ICU, NICU, ER)
- **Real-time Synchronization**: Firebase-powered real-time updates
- **Neonatal Age Calculations**: Automatic HOL (Hours of Life) / DOL (Days of Life) tracking
- **Plan Logging**: Track patient treatment plans with timestamps
- **Print/Export**: Generate handover reports for different shifts
- **Dark Mode**: Toggle between light and dark themes
- **PWA Support**: Install as a progressive web app

## Security Considerations

⚠️ **IMPORTANT**: This application handles Protected Health Information (PHI).

### Before Production Deployment:

1. **Enable Authentication**
   - Implement Firebase Authentication
   - Update `firestore.rules` to require authentication
   - Uncomment production-ready security rules

2. **HIPAA Compliance** (for US deployments)
   - Sign Firebase BAA (Business Associate Agreement)
   - Enable audit logging
   - Implement data encryption at rest
   - Set up proper backup procedures

3. **Security Rules**
   - Current rules allow open access for development
   - Update rules in `firestore.rules` before going live
   - Review and test all security rules

4. **Environment Variables**
   - Move Firebase config to environment variables
   - Use Firebase App Check to prevent API abuse

## Setup

1. Install Firebase CLI:
   ```bash
   npm install -g firebase-tools
   ```

2. Login to Firebase:
   ```bash
   firebase login
   ```

3. Initialize Firebase:
   ```bash
   firebase init
   ```

4. Deploy Firestore rules:
   ```bash
   firebase deploy --only firestore:rules
   ```

5. Deploy hosting:
   ```bash
   firebase deploy --only hosting
   ```

## Local Development

Open `index.html` in a web browser or use a local server:

```bash
python3 -m http.server 8000
# or
npx serve
```

## Firebase Configuration

The Firebase configuration is currently embedded in the HTML file. For production:
- Move to environment variables
- Enable Firebase App Check
- Implement proper authentication

## Data Structure

### Patient Document
- `name`: Patient name
- `id`: Patient ID
- `doa`: Date of admission
- `dob`: Date of birth (for neonatal calculations)
- `dot`: Time of birth (for neonatal calculations)
- `age`: Age display
- `bed`: Bed number
- `sex`: Patient sex
- `weight`: Patient weight
- `diagnosis`: Medical diagnosis
- `medications`: Current medications
- `issues`: Current issues
- `hopi`: History of present illness
- `ward`: Current ward
- `plan`: Treatment plan
- `logs`: Historical plan logs
- `isNew`: New patient flag
- `isAutoAge`: Auto-calculate age flag
- `shift`: Admission shift
- `timestamp`: Creation timestamp
- `dischargeTimestamp`: Discharge timestamp

## License

Private - Medical Use Only

## Support

For issues and questions, contact the development team.
