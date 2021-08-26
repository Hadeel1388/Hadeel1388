- usage: blinkistscraper [-h] [--language {en,de}] [--match-language]
                       [--cooldown COOLDOWN] [--headless] [--audio]
                       [--concat-audio] [--keep-noncat] [--no-scrape]
                       [--book BOOK] [--daily-book] [--books BOOKS]
                       [--book-category BOOK_CATEGORY]
                       [--categories CATEGORIES [CATEGORIES ...]]
                       [--ignore-categories IGNORE_CATEGORIES [IGNORE_CATEGORIES ...]]
                       [--create-html] [--create-epub] [--create-pdf]
                       [--save-cover] [--embed-cover-art] 
                       [--chromedriver CHROMEDRIVER] [--no-ublock] [--no-sandbox] [-v]
                       email password

positional arguments:
  email                 The email to log into your premium Blinkist account
  password              The password to log into your premium Blinkist account

optional arguments:
  -h, --help            show this help message and exit
  --language {en,de}    The language to scrape books in - either 'en' for
                        english or 'de' for german
  --match-language      Skip scraping books if not in the requested language
                        (not all book are avaible in german)
  --cooldown COOLDOWN   Seconds to wait between scraping books, and
                        downloading audio files. Can't be smaller than 1
  --headless            Start the automated web browser in headless mode.
                        Works only if you already logged in once
  --audio               Download the audio blinks for each book.
  --concat-audio        Concatenate the audio blinks into a single file and
                        tag it. Requires ffmpeg
  --keep-noncat         Keep the individual blink audio files, instead of
                        deleting them (works with '--concat-audio' only)
  --no-scrape           Don't scrape the website, only process existing json
                        files in the dump folder. Do not provide email or
                        password with this option.
  --book BOOK           Scrapes this book only, takes the Blinkist URL for the
                        book (e.g. https://www.blinkist.com/en/books/... or
                        https://www.blinkist.com/en/nc/reader/...)
  --daily-book          Scrapes the free daily book only.
  --books BOOKS         Scrapes the list of books, takes a txt file with the
                        list of Blinkist URL's for the books (e.g.
                        https://www.blinkist.com/en/books/... or
                        https://www.blinkist.com/en/nc/reader/...)
  --book-category BOOK_CATEGORY
                        When scraping a single book, categorize it under this
                        category (works with '--book' and '--daily-book' only)
  --categories CATEGORIES [CATEGORIES ...]
                        Only the categories whose label contains at least one
                        string here will be scraped. Case-insensitive; use
                        spaces to separate categories. (e.g. '--categories
                        entrep market' will only scrape books under
                        'Entrepreneurship' and 'Marketing & Sales')
  --ignore-categories IGNORE_CATEGORIES [IGNORE_CATEGORIES ...]
                        If a category label contains anything in
                        ignored_categories, books under that category will not
                        be scraped. Case-insensitive; use spaces to separate
                        categories. (e.g. '--ignored-categories entrep market'
                        will skip scraping of 'Entrepreneurship' and
                        'Marketing & Sales')
  --create-html         Generate a formatted html document for the book
  --create-epub         Generate a formatted epub document for the book
  --create-pdf          Generate a formatted pdf document for the book.
                        Requires wkhtmltopdf
  --save-cover          Save a copy of the Blink cover artwork in the folder
  --embed-cover-art     Embed the Blink cover artwork into the concatenated
                        audio file (works with '--concat-audio' only)
  --chromedriver CHROMEDRIVER
                        Path to a specific chromedriver executable instead of
                        the built-in one
  --no-ublock           Disable the uBlock Chrome extension. This will
                        completely skip the installation (and setup) of
                        ublock. If you want to use ublock content blocking, then
                        run the script again without this flag.
  --no-sandbox          When running as root (e.g. in Docker), Chrome requires
                        the '--no-sandbox' argument     
  -v, --verbose         Increases logging verbosity
