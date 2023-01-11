FROM python:3.10-slim AS production
WORKDIR /app
COPY pyproject.toml /app
RUN pip install .
COPY myapp /app/myapp
CMD ["uvicorn", "myapp.main:app"]

FROM production AS test
RUN pip install .[test]
COPY tests /app/tests
