## What is this project?

This repository is a python project that consumes the API of www.timeoff.gr.

The main functionality of the tool is to export documents from leave requests.

## How to install

This is a python project, and it's installed as follows:

1. Download the project from GitHub
2. Store the project in a folder
3. Run the following command to install the project:

```bash
pip install -r requirements.txt
```

## How to run

The project is runs as follows:

```bash
python timeoff_export_docx.py
```

## How to configure

### Configure the project

The configuration of the project is done via the file `config.ini`. The file is a standard INI file, and it is self-explanatory.

### Configure the template word documents

- The template word documents should be stored in the folder `templates`. Depending on the status of employment they should be placed either in directory `templates/permanent` or `templates/temporary`.
- Templates for the same leave type should always have the same filename.
- The template word documents must be `.docx` files, not `.doc` files.
- Each of the template documents should be related to a specific leave type.
- The name of the template document should be the one set on the field 'Description', of the related leave type, in `timeoff.gr` application.
- The tool will replace the following placeholders in the template documents:
  - `${TODAY}`: The current date, in the format specified in the configuration file with the key `date_format`
  - `${FIRSTNAME}`: The first name of the employee
  - `${LASTNAME}`: The last name of the employee
  - `${DEPARTMENT}`: The department of the employee
  - `${LEAVE_TYPE}`: The leave type of the leave request
  - `${REQUEST_DATE}`: The request date of the leave request, in the format `dd/mm/yyyy`
  - `${START_DATE}`: The start date of the leave request, in the format specified in the configuration file with the key `date_format`
  - `${END_DATE}`: The end date of the leave request, in the format specified in the configuration file with the key `date_format`
  - `${DAYS_COUNT}`: The number of days of the leave request
  - `${REASON}`: The reason of the leave request
  - `${REASON_AUTH1}`: The first authorization of the reason of the leave request
  - `${REASON_AUTH2}`: The second authorization of the reason of the leave request

