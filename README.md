# BAYES' THEOREM

An interactive Jupyter notebook that visualizes conditional probability and the **base-rate fallacy** through the example of comparing deaths 

from a disease against deaths from a vaccine's side effects.

Each of the 1,000,000 squares in the grid is one person, coloured by vaccination status and outcome. 

Three sliders let you reshape the population in real time, alongside a death-cause bar chart and a small optimization plot for the immunity level
that minimizes total deaths.





## Base-rate fallacy and denominator neglect

Misinformation often claims that *"vaccines are as lethal as the diseases they prevent"* by pointing at raw death counts. 

The tool shows why this is a base-rate fallacy (specifically *denominator neglect*): 

comparing the number of deaths in each group while ignoring how many people were at risk in each.



Slide `immunity` up to about 0.999 and the two death counts equalise at roughly 10 each. 

Superficially that looks like equal danger but the denominators are not equal:

* \~10 side-effect deaths come from \~999,000 vaccinated people → per-person
risk ≈ 0.00001
* \~10 disease deaths come from only \~1000 unvaccinated people → per-person
risk = 0.01

Same numerator, vastly different denominator: the disease is about 10,000×more lethal per person. 

This is Bayes' theorem made visible:

P(vaccinated | died) = P(died | vaccinated) · P(vaccinated) / P(died)

The base rate P(vaccinated) (the `immunity` slider) is what drives the
posterior up, not any change in how safe the vaccine actually is.

The linear optimization problem shows that these results hold for as long as the vaccine is safer (leads to a side-effects rate lower) than disease lethality. 





## Run

**Online (interactive, no install):** 

open in Google Colab


**Locally / VS Code:**

pip install -r requirements.txt

then open `bayes\_base\_rate\_fallacy.ipynb` and run all cells. 

In VS Code you also need the **Jupyter** extension installed.





## Note on the GitHub preview

GitHub renders notebooks statically and does not run code, so the sliders are
**not** interactive in the preview here and the plots (which render inside widget output areas) may not appear. 

Use the Colab link above for the live
version, or run it locally.

## 

