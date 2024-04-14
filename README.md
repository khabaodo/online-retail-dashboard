# Objective
Develop a practical and efficient dashboard that enables the store owner to swiftly oversee store operations and project sales revenue for the upcoming two months. This dashboard will serve as a valuable tool for examining product sales trends, which is essential for planning and ensuring adequate inventory levels for future demand.

# Methodology
## Preference
* Data source: Chen,Daqing. (2019). Online Retail II. UCI Machine Learning Repository. https://doi.org/10.24432/C5CG6D.
* Time series textbook: Diebold, F.X. (2001), Elements of forecasting, Department of Economics, University of Pennsylvania, http://www.ssc.upenn.edu/~fdiebold/Textbooks.html.
* I also got very useful advices from professor Markum Reed and professor Bradley Kamp at the University of South Florida (USF).
## Analytical techniques
* Data cleaning and feature engineering with Python
* Multidimensional analysis and building dashboard with Tableau
* Time series analysis and forecasting with RATS and Python

## Project management and milestones
I use Franklin planner to plan phases of the project and Burndown Chart to keep track the project progress. The project has some important milestones:
* **Find the data source**: The initial idea of the project was to create an interactive Tableau dashboard to raise awareness about climate change. However, due to time limit and the lack of domain knowledge in climate change, I decided to change the project topic to building a Tableau dashboard for business usage, the topic I am more familiar with.
* **Learn time series analysis and forecasting techniques**: Topics I learned are modelling and forecasting trends, seasonality, and cycles using Box-Jenkin approach, specifically ARIMA model. Other topics included VAR, combining forecast using variance-covariance method, and regression methods. I also briefly went over smoothing techniques, especially exponential smoothing.
* **Data cleaning and feature engineering with Python**: I wrote functions to clean the data with the help of Google Gemini.
* **Model development and training in RATS**: The series is not stationary and I tried 2 methods to make it covariance stationary: detrending & deseasonalizing and first-order differencing. I find the detrending & deseasonalizing method more interpretable so I chose this method. The best model specification can be found in in the *'OLS, residual plots, correlogram.pdf'* file. The code to reproduce the results can be found in the *'model_selection_rats.rpf'* file. After making the series stationary, I expected that the series would follow an ARMA process but the residual turned out to be white noise. I find the result not surprising as it is reasonable to expect the sales of a store to follow seasonality, not the sales in the past.
* **Tableau dashboard development**: The dashboard includes metrics like total revenue, total cost, profit, profit margin, and other useful information about the product. It also have the forecast section for future total revenue. Initially, I planned to use TabPy to process everything in Tableau using Python code; However, I find this rather complicated. So I use Python to preprocess the data and make forecast result. Subsequently, I use Tableau to visualize those results.
* **Testing and Refinement**: I refined the dashboard based on feedback, improving clarity, functionality, and user experience.
* **Documentation and Presentation**: I prepared a comprehensive project report detailing methodology, results, and limitations. I created a video presentation summarizing key findings and showcasing the interactive dashboard, which can be found here: [insert Youtube link]

## Results and limitations
The product is an effective Tableau dashboard for the store owner to efficiently manage store operations and forecast sales revenue for the next two months.

The dashboard has several limitations:
* **Lack features**: When building the model, the data is the most important part. However, although the data I used has about 1 million observations. However, it lacks important features e.g cost structures, plan of closing dates, and important selling dates. This dashboard serves as a prototype. To be fully usuable in the real world, more dimensions of the data is needed. To temporarily solve this problem, create a cost column in the data to find calculate net profit and profit margin.
* **Model building method**: To forecast time series model, I use the OLS/ARIMA approach. However, I can use panel data analysis techniques to capture the relationship bewtween different products thus produce a more accurate forecast. Due to the lack of time, I have not had the time to learn panel data. Another approach I can use instead of OLS/ARIMA is exponential smoothing. The advantage of exponential smoothing is that it is easy to build and can be applied to a vast amount of products. However, in this project, I prioritize interpretability over ease of building the model, so I chose the OLS/ARIMA approach.
* **Dashboard update in real-time**: Currently, to process the data, I have to run the Python code. I have yet found a way to automate the process when we have more data. The end goal is to connect Tableau to a server and possibly process the data using Python and connect the script to Tableau using TabPy. This is the possibility for improvements in the future.

# Conclusion
This project successfully developed a practical and efficient Tableau dashboard to  fulfill the store owner's needs. The dashboard offers a comprehensive overview of store operations, including key metrics like total revenue, profit, and profit margin.  Furthermore, it provides valuable insights into product sales trends through  forecasting revenue for the next two months.

This initial prototype demonstrates the potential of data-driven dashboards for informed decision-making in retail businesses. However, there's  room for improvement.  Future iterations could incorporate a wider range of data  points, such as cost structures and sales promotions, to enhance the accuracy of  forecasts. Additionally, exploring alternative modeling techniques like panel data  analysis or exponential smoothing could provide further insights. Finally, automating  data processing through real-time connections would significantly improve the  dashboard's usability.


