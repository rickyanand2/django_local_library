# django_local_library

# 🧠 Django MDN Tutorial — Personal Notes & MVP Mapping

## ✅ Models

### Book
- Fields: title, author, summary, ISBN, genre
- Uses `ManyToManyField` for genre
- **MVP Mapping**: Replace with `Vendor` (name, sector, contact_email)
- **Pro Tip**: Create `Vendor` model with slug field for cleaner URLs

### BookInstance
- Tracks individual book copies
- Uses `status`, `due_back`
- **MVP Mapping**: Use for `Assessment` model (linked to Vendor)
- **Pro Tip**: Build `AssessmentHistory` like this if needed later

---

## ✅ Views

### ListView
- Shows a list of model instances
- Uses `model = Book`, `context_object_name`
- **MVP Mapping**: Use for VendorList, AssessmentList
- **Pro Tip**: Pagination (`paginate_by = 10`) makes UI scalable

### DetailView
- Shows one model instance
- Renders with `pk` in URL
- **Pro Tip**: Use for vendor profile + risk score dashboard

---

## ✅ Forms

- Uses `ModelForm` for Book and Renewal
- Clean and reusable
- **Pro Tip**: Use `ModelForm` for vendor input and risk questionnaire

---

## ✅ Templates

- Uses `base_generic.html` as layout
- Includes `{% block title %}`, `{% block content %}`
- **MVP Mapping**: Reuse same structure for Bootstrap layout
- **Pro Tip**: Create `base.html` with navbar, alerts, footer

---

## ✅ Admin & Permissions

- Shows how to register custom admin models
- Uses `@login_required` and user roles
- **Pro Tip**: MVP phase → Use Django admin until public dashboard needed

---

## 🚀 Custom Features to Build Later

| Feature | MDN Equivalent | Notes |
|---------|----------------|-------|
| Custom User Login | CustomUser later | Add after core flow is working |
| Questionnaire | Book renewal form | Use `ModelFormSet` or form wizard |
| PDF Export | Manual extension | Use WeasyPrint after risk score logic is done |
