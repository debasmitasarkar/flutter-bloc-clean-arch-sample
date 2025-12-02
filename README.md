# Flutter Clean Architecture Sample

A Flutter application demonstrating **Clean Architecture** principles with **BLoC/Cubit** state management — built to showcase scalable, testable, and maintainable Flutter patterns.

---

## ✨ Features

- Paginated list with infinite scroll (10 items per page)
- Multi-criteria filtering (type + date range)
- Loading states with shimmer skeletons
- Empty and error state handling
- Comprehensive test coverage

---

## 🗂 Project Structure (Clean Architecture)
```text
lib/
├── core/               # Cross-cutting concerns (network, errors, utils)
├── features/
│   └── absences/
│       ├── data/       # DTOs, datasources, mappers, repository impl
│       ├── domain/     # Entities, repository contracts, use-cases
│       └── presentation/
│           ├── cubit/  # AbsenceCubit & states
│           ├── pages/  # AbsencesPage (UI)
│           └── widgets/# AbsenceCard, StatusPill, Note, …
└── api/                # Local package simulating remote API
```

### 🔄 Data Flow
```text
API → DataSource → Repository → UseCase → Cubit → UI
         ↓              ↓            ↓
   Either<Failure, DTO> → Either<Failure, Entity>
```

---

## 📦 Tech Stack

| Package | Purpose |
|---------|---------|
| `flutter_bloc` | BLoC/Cubit state management |
| `dartz` | Functional programming (Either, Right/Left) |
| `get_it` | Dependency injection |
| `equatable` | Value equality for states |
| `shimmer` | Skeleton loading effects |
| `mocktail` / `bloc_test` | Testing utilities |

---

## 🚀 Getting Started
```bash
git clone https://github.com/debasmitasarkar/flutter-bloc-clean-arch-sample.git
cd flutter-bloc-clean-arch-sample

# Install dependencies
flutter pub get

# Generate DTOs
flutter pub run build_runner build --delete-conflicting-outputs

# Run
flutter run
```

> Requires **Flutter 3.22+** and **Dart 3.3+**

---

## 🧪 Tests
```bash
flutter test
```

Coverage includes: datasources, mappers, repository logic, Cubit state transitions, and widget tests.

---

## 📄 License

MIT
