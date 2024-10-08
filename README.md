# Django Markdown Editor Next

An advanced Markdown editor for Django admin with real-time preview, image uploads, and customizable toolbar. This package extends and improves upon existing Django Markdown editors.

## Installation

```bash
pip install django-markdown-editor-next
```

## Setup

1. Add 'django_markdown_editor_next' to your INSTALLED_APPS setting.

2. Add the following to your project's urls.py:

   ```python
   from django.urls import path, include

   urlpatterns = [
       # ... your other url patterns
       path('markdown-editor-next/', include('django_markdown_editor_next.urls')),
   ]
   ```

3. Ensure your `MEDIA_ROOT` and `MEDIA_URL` settings are configured in your Django settings:

   ```python
   MEDIA_ROOT = BASE_DIR / 'media'
   MEDIA_URL = '/media/'
   ```

4. In your models, use the MarkdownField:

   ```python
   from django_markdown_editor_next.fields import MarkdownField

   class MyModel(models.Model):
       content = MarkdownField()
   ```

## Features

- Real-time Markdown preview
- Image uploads with drag-and-drop support
- Customizable toolbar
- Keyboard shortcuts
- Syntax highlighting for code blocks
- Emoji picker

## Customizing the Toolbar

You can customize the toolbar buttons when defining your model field:

```python
content = MarkdownField(
    custom_toolbar=[
        {'action': 'bold', 'icon': 'fas fa-bold', 'title': 'Bold'},
        {'action': 'italic', 'icon': 'fas fa-italic', 'title': 'Italic'},
        {'action': 'link', 'icon': 'fas fa-link', 'title': 'Link'},
        {'action': 'image', 'icon': 'fas fa-image', 'title': 'Image'},
        {'action': 'preview', 'icon': 'fas fa-eye', 'title': 'Toggle Preview'},
        {'action': 'emoji', 'icon': 'fas fa-smile', 'title': 'Insert Emoji'}
    ]
)
```

## Keyboard Shortcuts

- Ctrl/Cmd + B: Bold
- Ctrl/Cmd + I: Italic
- Ctrl/Cmd + K: Insert Link
- Ctrl/Cmd + Shift + C: Insert Code Block

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.