# Working backwards for a more sustainable world: An NLP-based empirical analysis of supply chain sustainability efforts in the consumer sector

This repository holds the code I wrote for my thesis for the MSc in Social Data Science at the University of Oxford, Oxford Internet Institute (OII). The code was used to analyse 1,113 ESG reports from 232 consumer companies (89,491 pages in total), from the data collection and processing through to the descriptive and statistical analysis. I implemented both BERT classification models (which I compared to a number of baseline models) and an LDA topic model.

The code is written in a series of Jupyter Notebooks that can be found in the Code folder:
- **00_text_processing.ipynb**: Extracts text from PDFs given an Excel with PDF links and/or filenames; cleans text; and saves a report details dataframe and a paragraphs dataframe
- **01_select_data_to_label.ipynb**: Selects 10% of the paragraphs for hand-labelling
- **02_train-test-val_split.ipynb**: Loads the hand-labelled paragraphs and creates train, test, and validation sets (stratified by label)
- **03_baseline_models_and_bootstrap.ipynb**: Builds baseline models (keyword-based dictionary, Naive Bayes, and SVM) and runs a bootstrap test to see performance across 30 runs
- **04_BERT_models.ipynb**: Finetunes BERT models (from both bert-base-uncased and a domain-specific model)
- **05_BERT_models_bootstrap.ipynb**: Runs a bootstrap test to see BERT model performance across 30 runs
- **06_visualize_bootstrap_test.ipynb**: Visualizes model performance from the bootstrap test (incl. both baseline and BERT models)
- **07_predictions_from_BERT.ipynb**: Generates predictions from best models (all were BERT)
- **08_alt_predictions_from_BERT.ipynb**: Generates predictions from second-best models (2 of which were BERT)
- **09_alt_predictions_from_SVM.ipynb**: Generates predictions from second-best models (2 of which were SVM)
- **10_topic_model_tuning.ipynb**: Tunes LDA topic model to identify best number of topics (k)
- **11_final_topic_model.ipynb**: Builds final LDA topic model and gets topic classification for each paragraph
- **12_variable_creation.ipynb**: Creates necessary variables and final dataframes for analysis; here, I import other external data (company & industry data from S&P Capital IQ, Eikon Refinitiv, and NSF's Annual Business Survey)
- **13_descriptive_analyses.ipynb**: Calculate descriptive statistics and create visualizations
- **14_stats_kruskal-wallis.ipynb**: Uses Kruskal-Wallis test to check for sub-sector differences in ESG supply chain content
- **15_stats_regression.ipynb**: Uses fixed effects regression to test hypotheses on public opinion and leadership characteristics

Note: Notebooks 04, 05, 07, 08, and 10 were run in Google Colab (used GPU, high-RAM for BERT code)

For a quick look at the visual outputs, see the Figures folder.
