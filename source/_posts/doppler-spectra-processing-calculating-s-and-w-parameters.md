---
title: Doppler spectra processing. Calculating S and W parameters.
date: 2017-02-03 00:49:26
tags:
thumbnail: thumbnail.gif
---

In this post we will discuss the process of calculating the S and W integration parameters from two-dimentional doppler histograms.
<!--more-->

<h2>Introduction</h2>
One of the crucial material characterization facility in our lab is Doppler positron spectrometer. Our two-detector setup utilizes a pair of hyperpure germanuim detectors connected to digital LYNX analyzers produced by Canberra.

Acquisition of spectra is controlled by <a href="http://www.canberra.com/products/radiochemistry_lab/prospect-software.asp">ProSpect</a> desktop app. ProSpect app works in so-called Timestamp (TLIST) mode when system registers annihilation photon energy and moment of time when photon was registered. Having this information provided for both detectors we can match the photons that arrived to every detector at the same moment. This pair of photons comes from the same positron-electron annihilation event.

Reconstruction of two-dimensional Doppler-broadened energy spectrum is continuously performed during the acquisition process by means of <a href="http://www.canberra.com/products/research/education-lab-kits_tlist.asp">TLIST Data Scanner</a> software. We will cover the spectra acquisition prosess in a separate post later.

In this tutorial I will demonstrate only the process of processing 2D spectrum and extracting S and W integration parameters.

We will use two desktop apps, namely <a href="http://physics.bgsu.edu/selimlab/selimlab/doppler-annihilation-radiation-software">TLIST Processor</a> and <a href="http://physics.bgsu.edu/selimlab/selimlab/s-w-doppler-parameters-software">SW Calculator</a>. Executable files are hosted on GitHub repository. Correspondent download links are provided on the <a href="http://physics.bgsu.edu/selimlab/selimlab/software">Software page</a> on our website. Alternatively we have windows executables located in our Dropbox folder <a href="https://www.dropbox.com/sh/buqs5iarnvm8wn0/AABHqBWhy3CZZlbHGG-9Vi8Ea?dl=0">/SelimLab Public Folder/Doppler Broadening/Software/</a>.
<h2>Running Doppler apps on your Personal Computer</h2>
Majority of us works on windows machines. In order to run both TLIST Processor and SW Calculator apps on your Windows PC one has to download and install <a href="https://www.microsoft.com/en-us/download/details.aspx?id=48138">Microsoft Visual Studio 2013</a> first. For BGSU students there is a way to obtain a free version of this software. Go to their <a href="https://www.visualstudio.com/free-developer-offers/">official website here</a> and find "Join Now" button on the bottom. Login using your BGSU credentials. Open "Downloads" tab in the top menu. Select "Developer Tools" item in the left menu. Scroll down until you find "Visual Studio 2013 <strong>with</strong> Update 5" item in the list. There is a search bar Grab it and install.

Secondly, we will need to install some extra libraries, namely <a href="https://root.cern.ch/">CERN ROOT framework</a>. Setup on a Windows machine is quite straightforward. You download CERN ROOT windows setup executable <a href="https://root.cern.ch/download/root_v5.34.36.win32.vc12.exe">from its official website</a>. When following the install wizard steps make sure you select an option to add ROOT libraries path to system's PATH environment variable. This option will be located on one of the last wizard steps.

Now let's assume you have installed all the stuff you need and you can run both TLIST Processor and SW Calculator apps. If for some reason there is any problem running any of them you can always use Doppler PC in 180 Overmann Hall.

<h2>Obtaining one-dimensional Doppler spectrum</h2>
First thing we need to take the two-dimensional spectrum file that was exported in TLIST Data Scanner app and convert it to one-dimensional one. We will do that with TLIST DataScanner App. For a test please <a href="https://www.dropbox.com/s/rygx56z0b6bkwha/test-spectrum.txt?dl=0">download this ZnO spectrum</a>. Make a special folder for this spectrum and save it to your hard drive.
<ol>
 	<li>Run TLIST Processor app. Click "Open File" button on the top left. Locate your spectrum in the Open dialog window. To the right of the "Open File" button you have two different spectrum filtering options.</li>
 	<li>First option says "Subtract Background". It's our new technology which should work more accurate with spectra having more than 1000 counts in the maximum bin. Another option - "Cut diagonal events" is a traditional method widely used in positron community. I will cover the discrepancies some time later. Anyway it's interesting to try every filtering option and see how different S and W parameters will be.</li>
 	<li>To start projecting and filtering the data press "Process Spectrum" button on the right. For some reason it takes some time to do the projection so kick back and be patient. The app user interface fill freeze for about 5 minutes.</li>
 	<li>Finally, click "Save Doppler Spectrum" on the bottom right. Optionally, hit "Export Images" button to save the pictures. Images are saved in the same folder along with your spectrum file. One-dimensional spectrum filename will be the same as the input file with appended "-doppler" suffix.</li>
</ol>

{% img "w-100 mt-2" /doppler-spectra-processing-calculating-s-and-w-parameters/tlist-processor.png "'TLIST Processor how-to'" %}

<h2>Calculating S and W parameters</h2>
Next we will take the one-dimensional spectrum that was saved by TLIST Processor and Open it in SW Calculator app in order to obtain the integration parameters.
<ol>
 	<li>Open the app. Click "Open File" button on the top left. Locate your 1D doppler spectrum file in the Open File dialog. After you open the file its contents will be reflected in the window below.</li>
 	<li>Hit "Import Spectrum" button. The spectrum histogram will appear in the bottom window. Make sure that it looks adequate. For two-detector setup everything should work out of the box. Doppler spectra acquired with single germanium detector will have slightly different format and one should change the Energy and Counts Column numbers in order for the spectrum to be imported successfully.</li>
 	<li>Notice the "Fit Data" tab became enabled. Open it.</li>
</ol>
{% img "w-100" /doppler-spectra-processing-calculating-s-and-w-parameters/swc-1.png "'SW Calculator 1'" %}

<ol start="4">
 	<li>On the "Fit Results" tab adjust the "Fit Range" to be wide enough. Make sure that full Doppler spectrum hump will be visible in preview window. S and W parameters are ratios of the gray areas under the curve to the full area under the spectrum. Apparently if you select only part of the spectrum the normalization will be incorrect.</li>
 	<li>Check "2 detector setup" checkbox above the "Fit" button. Later we might tweak the app to automatically detect this setting.</li>
 	<li>Press "Fit and Calculate" button. Actually as of now the fit procedure is rudimentary. Currently we fit the spectrum with a number of gaussian functions. Later we plan to fit the tip of the curve with parabola which will represent the Fermi surface for electrons in metals.</li>
 	<li>If you want to copy S and W values - select them and use right-click. Keyboard CTRL+C does not work in that widget.</li>
 	<li>Save images by clicking "Save Image" button. If you want to plot the preview window data in Origin - save data points by clicking "Export Fit Data" button. Again all the files are saved in the same folder where your original spectrum was located.</li>
</ol>

{% img "w-100" /doppler-spectra-processing-calculating-s-and-w-parameters/swc-2.png "'SW Calculator 2'" %}

I'm going to update this post with more detailed explanations on Doppler experimental data processing later on. Stay tuned!