# Lab 01 Deliverables

> **Canvas submission:** Upload one PDF containing a clear, curated compilation
> of the required Part I results below. Include the relevant calculations,
> tables, plots, screenshots, and brief explanations in a logical order; an
> additional extensive report is not expected. The filenames below are helpful
> for organizing your working files and are not separate Canvas uploads.

> **Four models are required:** Two-Ray Ground, COST231-Hata, Friis, and Nakagami.
> Starter code and instructions exist for all four.
>
> **Part I contains the required deliverables. Part II is an optional extension
> for additional practical experience.**

## Part I – Simulation (ns-3)

For each of the four propagation models (Two-Ray Ground, COST231-Hata, Friis, Nakagami):

1. **Initial distance calculation**

   * Show how you determined the initial distance *di* (the border of the transmission range) for each model.
   * Suggested working filename: `initial_distance_<model>.txt` (e.g. `initial_distance_friis.txt`).

2. **Simulation results**

   * Run experiments at 8 distances: {di, 7di/8, 6di/8, …, di/8}.
   * For each model, produce:

     * `<model>_results.csv` — columns: `distance,bitrate`.
     * `<model>_plot.png` — plot of bitrate vs. distance.

3. **Bitrate calculation evidence**

   * Provide one example Wireshark screenshot (sender & receiver PCAP) showing how you measured bitrate.
   * Suggested working filename: `<model>_wireshark.png` for any one model of your choice.

---

## Part II – Practical Measurement (Optional)

If you choose to complete this optional exercise, the following suggested
outputs can help you organize your results. They are separate from the required
Part I deliverables.

1. **Measured RSSI values**

   * Capture RSSI at different distances in a corridor (with at least one corner, as in Fig. 3 of the lab handout).
   * Suggested filename: `measured_rssi.csv` — columns: `distance,rssi_dbm`.

2. **Path loss calculations**

   * Compute path loss (Tx power – RSSI).
   * Suggested filename: `measured_pathloss.csv` — columns: `distance,path_loss_db`.
   * Also compute theoretical path loss with Friis at the same distances.
   * Suggested filename: `friis_pathloss.csv`.

3. **Plots**

   * `pathloss_comparison.png` — plot measured vs Friis path loss.

4. **Discussion**

   * In `discussion.txt`, answer: *Does the Friis model mimic the measured path loss? Why or why not?*

---

## Suggested Working File Names (Required Part I Results)

* `initial_distance_friis.txt`, `initial_distance_tworay.txt`, `initial_distance_cost231.txt`, `initial_distance_nakagami.txt`
* `friis_results.csv`, `tworay_results.csv`, `cost231_results.csv`, `nakagami_results.csv`
* `friis_plot.png`, `tworay_plot.png`, `cost231_plot.png`, `nakagami_plot.png`
* `<model>_wireshark.png` (any one)

## Suggested Optional Part II Filenames

* `measured_rssi.csv`
* `measured_pathloss.csv`
* `friis_pathloss.csv`
* `pathloss_comparison.png`
* `discussion.txt`

---

**All CSV files must have headers. All plots must include labeled axes and legends.**
