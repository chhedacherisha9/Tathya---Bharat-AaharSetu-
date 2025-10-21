<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <title>Tathya - Bharat AaharSetu: Nutrition Label Interpreter & Calculator</title>
    <meta name="description" content="Nutrition, De-jargonized. Get your ingredient breakdown and whole-package nutrient story in seconds.">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f4f8;
        }
        .card {
            background-color: white;
            border-radius: 0.75rem;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1),
                        0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
    </style>
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'primary-blue': '#1e40af',
                        'light-blue': '#eff6ff',
                        'success-green': '#059669',
                    }
                }
            }
        }
    </script>
</head>

<body class="p-6">
    <!-- Header Section -->
    <header class="text-center mb-8">
        <h1 class="text-3xl md:text-4xl font-bold text-primary-blue mb-2">
            Tathya - Bharat AaharSetu
        </h1>
        <p class="text-gray-700 text-base md:text-lg">
            Nutrition, De-jargonized. Get your ingredient breakdown and whole-package nutrient story in seconds.
        </p>
    </header>

    <!-- Example Content Card -->
    <main class="max-w-3xl mx-auto">
        <div class="card p-6">
            <h2 class="text-2xl font-semibold text-primary-blue mb-4">
                Nutrition Label Interpreter
            </h2>
            <p class="text-gray-600">
                Enter your food product details below to get a complete nutrient profile, ingredient breakdown,
                and recommended insights powered by Google API and GitHub integration.
            </p>
        </div>
    </main>

    <!-- Optional Footer -->
    <footer class="text-center text-gray-500 mt-8 text-sm">
        © 2025 Tathya - Bharat AaharSetu | Made with 💚 for a healthier Bharat
    </footer>
</body>
</html>
<body class="p-4 md:p-8 min-h-screen">

    <div class="max-w-4xl mx-auto space-y-8">
        <header class="text-center">
            <h1 class="text-4xl font-extrabold text-primary-blue mb-2">Label Interpreter & Calculator</h1>
            <p class="text-gray-600">Understand your ingredients, check nutrient ranges, and calculate totals.</p>
        </header>

        <!-- Main Input Card -->
        <div class="card p-6 md:p-8">
            <h2 class="text-2xl font-bold text-gray-800 mb-6 border-b pb-3">1. Input Product Data</h2>
           
            <!-- Net Weight Input -->
            <div class="mb-6">
                <label for="netWeight" class="flex items-center text-lg font-semibold text-primary-blue mb-2">
                    <i data-lucide="scale" class="w-5 h-5 mr-2"></i> Net Weight of Product (Package Size)
                </label>
                <input type="number" id="netWeight" placeholder="e.g., 250" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-blue focus:border-primary-blue" min="1" value="100">
                <p class="text-sm text-gray-500 mt-1">Enter the total weight of the product in **grams**.</p>
            </div>

            <!-- Ingredients Input -->
            <div class="mb-6">
                <label for="ingredientsList" class="flex items-center text-lg font-semibold text-primary-blue mb-2">
                    <i data-lucide="list-ordered" class="w-5 h-5 mr-2"></i> Ingredients (Ordered by Quantity Percent)
                </label>
                <textarea id="ingredientsList" rows="4" placeholder="Enter one ingredient name per line, in order of highest quantity first (e.g., Wheat Flour, Refined Sugar, Palm Oil, Salt...)" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-blue focus:border-primary-blue">Wheat Flour
Refined Sugar
Palm Oil
Salt
Baking Powder</textarea>
                <p class="text-sm text-gray-500 mt-1">List names exactly as they appear on the label for best interpretation.</p>
            </div>

            <!-- Nutritional Information Input -->
            <div class="mb-8">
                <label class="flex items-center text-lg font-semibold text-primary-blue mb-3">
                    <i data-lucide="zap" class="w-5 h-5 mr-2"></i> Nutritional Information (Amount per 100 grams)
                </label>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
                    <!-- Energy -->
                    <div class="flex items-center bg-light-blue p-3 rounded-lg border border-primary-blue/30">
                        <span class="font-medium w-28">Energy (kcal):</span>
                        <input type="number" id="nut_energy" value="482" class="flex-grow p-1 border-b border-primary-blue/50 text-right focus:outline-none bg-transparent" min="0">
                    </div>
                    <!-- Protein -->
                    <div class="flex items-center bg-light-blue p-3 rounded-lg border border-primary-blue/30">
                        <span class="font-medium w-28">Protein (g):</span>
                        <input type="number" id="nut_protein" value="6.7" class="flex-grow p-1 border-b border-primary-blue/50 text-right focus:outline-none bg-transparent" min="0">
                    </div>
                    <!-- Carbohydrate -->
                    <div class="flex items-center bg-light-blue p-3 rounded-lg border border-primary-blue/30">
                        <span class="font-medium w-28">Carbs (g):</span>
                        <input type="number" id="nut_carbs" value="71.9" class="flex-grow p-1 border-b border-primary-blue/50 text-right focus:outline-none bg-transparent" min="0">
                    </div>
                    <!-- Sugar -->
                    <div class="flex items-center bg-light-blue p-3 rounded-lg border border-primary-blue/30">
                        <span class="font-medium w-28">Sugar (g):</span>
                        <input type="number" id="nut_sugar" value="25.0" class="flex-grow p-1 border-b border-primary-blue/50 text-right focus:outline-none bg-transparent" min="0">
                    </div>
                    <!-- Fat -->
                    <div class="flex items-center bg-light-blue p-3 rounded-lg border border-primary-blue/30">
                        <span class="font-medium w-28">Total Fat (g):</span>
                        <input type="number" id="nut_fat" value="19.0" class="flex-grow p-1 border-b border-primary-blue/50 text-right focus:outline-none bg-transparent" min="0">
                    </div>
                    <!-- Sodium -->
                    <div class="flex items-center bg-light-blue p-3 rounded-lg border border-primary-blue/30">
                        <span class="font-medium w-28">Sodium (mg):</span>
                        <input type="number" id="nut_sodium" value="350" class="flex-grow p-1 border-b border-primary-blue/50 text-right focus:outline-none bg-transparent" min="0">
                    </div>
                </div>
            </div>

            <!-- Action Button -->
            <button onclick="processLabelData()" id="processButton" class="w-full bg-primary-blue text-white p-4 rounded-lg font-bold text-xl hover:bg-primary-blue/90 transition-colors shadow-lg flex items-center justify-center">
                <i data-lucide="activity" class="w-5 h-5 mr-3"></i> Analyze Label
            </button>
            <div id="loadingIndicator" class="hidden text-center mt-4 text-primary-blue font-semibold">
                <div class="animate-spin inline-block w-6 h-6 border-4 border-primary-blue border-t-transparent rounded-full mr-2"></div>
                Analyzing ingredients...
            </div>
            <div id="errorMessage" class="hidden mt-4 p-3 bg-red-100 text-red-700 border border-red-400 rounded-lg" role="alert"></div>
        </div>
       
        <!-- Results Container -->
        <div id="resultsContainer" class="hidden space-y-8">
           
            <!-- Output 2: Total Nutrient Calculation & Range Check -->
            <div class="card p-6 md:p-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-4 flex items-center text-primary-blue">
                    <i data-lucide="calculator" class="w-6 h-6 mr-3"></i> 2. Total Nutrient Content (Per Package) & Range Check
                </h2>
                <div id="netWeightDisplay" class="text-lg font-semibold text-gray-700 mb-4">
                    Based on a Net Weight of <span class="text-primary-blue font-extrabold" id="calculatedNetWeight"></span> grams:
                </div>
               
                <div id="totalNutrientResults" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
                    <!-- Total nutrient cards will be injected here -->
                </div>

                <div class="mt-6 p-4 bg-yellow-50 rounded-lg border border-yellow-200 text-sm text-gray-700">
                    <p class="font-bold text-yellow-700 flex items-center mb-1"><i data-lucide="info" class="w-4 h-4 mr-2"></i> Range Note</p>
                    <p>The **High/Medium/Low** classification uses common international traffic light thresholds for quick assessment. **For official compliance, refer to the FSSAI Summary below.**</p>
                </div>
            </div>

            <!-- Output 3: FSSAI Compliance Summary (LLM Analysis) -->
            <div class="card p-6 md:p-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-4 flex items-center text-primary-blue">
                    <i data-lucide="shield-check" class="w-6 h-6 mr-3"></i> 3. FSSAI Compliance Summary
                </h2>
                <p class="text-gray-600 mb-4">An analysis of the nutritional data against the FSSAI regulations provided in your uploaded documents, focusing on relevant standards.</p>
                <div id="fssaiComplianceSummary" class="p-4 rounded-lg border bg-light-blue min-h-[100px] flex items-center justify-center">
                    <div class="text-gray-500 italic">... waiting for FSSAI analysis ...</div>
                </div>
            </div>

            <!-- Output 1: Ingredient Interpretation -->
            <div class="card p-6 md:p-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-4 flex items-center text-primary-blue">
                    <i data-lucide="message-square" class="w-6 h-6 mr-3"></i> 4. Ingredient Simple Explanations
                </h2>
                <p class="text-gray-600 mb-4">A simple, easy-to-understand breakdown of what each ingredient is and its function.</p>
                <div id="ingredientDescriptions" class="space-y-3">
                    <!-- Descriptions will be injected here -->
                </div>
            </div>

        </div>

    </div>

    <script type="module">
        // Helper function for exponential backoff (retry logic for API calls)
        const fetchWithRetry = async (url, options, maxRetries = 5) => {
            for (let i = 0; i < maxRetries; i++) {
                try {
                    const response = await fetch(url, options);
                    if (response.ok) {
                        return response;
                    }
                    // Throw error for bad response (4xx or 5xx) to trigger retry/catch
                    throw new Error(`HTTP error! status: ${response.status}`);
                } catch (error) {
                    if (i === maxRetries - 1) throw error;
                    const delay = Math.pow(2, i) * 1000; // Exponential backoff
                    console.warn(`Request failed, retrying in ${delay / 1000}s...`);
                    await new Promise(resolve => setTimeout(resolve, delay));
                }
            }
        };

        const API_MODEL = "gemini-2.5-flash-preview-09-2025";
        const apiKey = "AIzaSyBMsK-v6rOX5M6JGEzFkvR-nuwDj1tRNNk";
        const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/${API_MODEL}:generateContent?key=${apiKey}`;

        // Traffic Light Thresholds (Per 100g) based on general international guidelines
        // These are not FSSAI specific, but common global standards for quick assessment.
        const TRAFFIC_LIGHT_THRESHOLDS = {
            // High > 17.5g; Low < 3.0g
            fat: { high: 17.5, low: 3.0 },
            // High > 22.5g; Low < 5.0g
            sugar: { high: 22.5, low: 5.0 },
            // High > 600mg; Low < 120mg (Sodium)
            sodium: { high: 600, low: 120 },
        };

        // Function to classify nutrient status
        const classifyNutrient = (key, amountPer100g) => {
            const thresholds = TRAFFIC_LIGHT_THRESHOLDS[key];
            if (!thresholds) return { status: 'N/A', icon: 'zap', color: 'text-primary-blue', bg: 'bg-light-blue', border: 'border-primary-blue' };

            if (amountPer100g > thresholds.high) {
                return { status: 'High', icon: 'arrow-up-circle', color: 'text-red-600', bg: 'bg-red-100', border: 'border-red-600' };
            } else if (amountPer100g < thresholds.low) {
                return { status: 'Low', icon: 'arrow-down-circle', color: 'text-success-green', bg: 'bg-green-100', border: 'border-success-green' };
            } else {
                return { status: 'Medium', icon: 'minus-circle', color: 'text-yellow-600', bg: 'bg-yellow-100', border: 'border-yellow-600' };
            }
        };


        // Utility function to display errors
        const displayError = (message) => {
            const errorDiv = document.getElementById('errorMessage');
            errorDiv.textContent = `Error: ${message}`;
            errorDiv.classList.remove('hidden');
        }

        // Utility function to hide error and results (used at start of run)
        const hideResultsAndError = () => {
            document.getElementById('errorMessage').classList.add('hidden');
            document.getElementById('resultsContainer').classList.add('hidden');
        }

        // Utility function to stop loading and enable button (used in finally block)
        const stopLoadingUI = () => {
            document.getElementById('loadingIndicator').classList.add('hidden');
            document.getElementById('processButton').disabled = false;
            document.getElementById('processButton').innerHTML = '<i data-lucide="activity" class="w-5 h-5 mr-3"></i> Analyze Label';
        }
       
        /**
         * Step 1: Handle User Input and Start Processing
         */
        window.processLabelData = async () => {
            // Start by hiding any previous results or errors
            hideResultsAndError();
           
            const netWeightInput = document.getElementById('netWeight');
            const ingredientsListInput = document.getElementById('ingredientsList');
           
            const netWeight = parseFloat(netWeightInput.value);
            const rawIngredients = ingredientsListInput.value.trim();
           
            if (!netWeight || netWeight <= 0) {
                displayError("Please enter a valid Net Weight in grams.");
                return;
            }
            if (!rawIngredients) {
                displayError("Please enter at least one ingredient name.");
                return;
            }

            // Start loading state
            document.getElementById('processButton').disabled = true;
            document.getElementById('processButton').textContent = 'Analyzing...';
            document.getElementById('loadingIndicator').classList.remove('hidden');

            const ingredients = rawIngredients.split('\n').map(name => name.trim()).filter(name => name.length > 0);
           
            // Collect the per 100g data for subsequent analysis
            const per100gData = {
                energy: parseFloat(document.getElementById('nut_energy').value) || 0,
                protein: parseFloat(document.getElementById('nut_protein').value) || 0,
                carbs: parseFloat(document.getElementById('nut_carbs').value) || 0,
                sugar: parseFloat(document.getElementById('nut_sugar').value) || 0,
                fat: parseFloat(document.getElementById('nut_fat').value) || 0,
                sodium: parseFloat(document.getElementById('nut_sodium').value) || 0,
            };

            try {
                // Task 1: Calculate Total Nutrients & Traffic Light Check
                const analysisResults = calculateTotalNutrients(netWeight, per100gData);
               
                // Task 2: Get Ingredient Descriptions (LLM Call)
                await interpretIngredients(ingredients);
               
                // Task 3: FSSAI Compliance Summary (LLM Call using uploaded documents)
                await analyzeFSSAICompliance(analysisResults.totalResults, per100gData);

               
                // Show results upon successful completion
                document.getElementById('resultsContainer').classList.remove('hidden');
                document.getElementById('calculatedNetWeight').textContent = netWeight.toFixed(2);
                lucide.createIcons(); // Re-render icons after content injection

            } catch (e) {
                console.error("Overall processing error:", e);
                displayError(`Analysis failed. Please check your inputs or try again. LLM error: ${e.message}`);
            } finally {
                // Always stop loading, whether success or failure
                stopLoadingUI();
            }
        };

        /**
         * Task 1: Calculate Total Nutrients & Perform Traffic Light Check
         */
        const calculateTotalNutrients = (netWeight, per100gData) => {
            const resultsContainer = document.getElementById('totalNutrientResults');
            resultsContainer.innerHTML = ''; // Clear previous results
           
            const nutrientInputs = [
                { key: 'energy', label: 'Energy', unit: 'kcal' },
                { key: 'protein', label: 'Protein', unit: 'g' },
                { key: 'carbs', label: 'Carbohydrates', unit: 'g' },
                { key: 'sugar', label: 'Total Sugar', unit: 'g' },
                { key: 'fat', label: 'Total Fat', unit: 'g' },
                { key: 'sodium', label: 'Sodium', unit: 'mg' },
            ];

            const totalResults = [];

            nutrientInputs.forEach(nut => {
                const amountPer100g = per100gData[nut.key];
               
                // Calculation: (Amount per 100g / 100) * Net Weight
                const totalAmount = (amountPer100g / 100) * netWeight;
               
                const classification = classifyNutrient(nut.key, amountPer100g);

                const total = totalAmount.toFixed(nut.unit === 'kcal' ? 0 : 2); // Round kcal to nearest whole number

                // Define the result object here to use it in the template
                const nutrientResult = {
                    key: nut.key,
                    label: nut.label,
                    unit: nut.unit,
                    per100g: amountPer100g,
                    total: total,
                    classification
                };

                totalResults.push(nutrientResult);
               
                // Render the result card
                resultsContainer.innerHTML += `
                    <div class="${classification.bg} border-l-4 ${classification.border.replace('border-', 'border-')} p-4 rounded-lg shadow-md">
                        <div class="flex justify-between items-center">
                            <p class="text-sm font-medium text-gray-600">${nutrientResult.label}</p>
                            ${classification.status !== 'N/A' ? `<span class="px-2 py-0.5 text-xs font-semibold rounded-full ${classification.color} ${classification.bg.replace('bg-', 'bg-')}/70">${classification.status}</span>` : ''}
                        </div>
                        <p class="text-2xl font-bold ${classification.color} mt-1">
                            ${nutrientResult.total} <span class="text-base ${classification.color.replace('text-', 'text-')}">${nutrientResult.unit}</span>
                        </p>
                        <p class="text-xs text-gray-500 mt-1">(${nutrientResult.per100g.toFixed(2)} ${nutrientResult.unit} per 100g)</p>
                    </div>
                `;
            });
           
            return { totalResults, per100gData };
        };

        /**
         * Task 2: Interpret Ingredients using Gemini API
         */
        const interpretIngredients = async (ingredients) => {
            const userQuery = `Provide a very simple, single-sentence explanation for each of the following ingredients, focusing on its common source or primary function in food. The ingredients are: ${ingredients.join(', ')}.`;
           
            const systemPrompt = "You are an expert food scientist and tutor. Your role is to take a list of ingredients and provide a very simple, single-sentence, easy-to-understand explanation of what each ingredient is, focusing on its common source or function. Do not use complex jargon. Respond ONLY with a JSON array.";

            // Construct the payload for structured JSON output
            const payload = {
                contents: [{ parts: [{ text: userQuery }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] },
                generationConfig: {
                    responseMimeType: "application/json",
                    responseSchema: {
                        type: "ARRAY",
                        items: {
                            type: "OBJECT",
                            properties: {
                                "ingredientName": { "type": "STRING" },
                                "simpleDescription": { "type": "STRING" }
                            },
                            "propertyOrdering": ["ingredientName", "simpleDescription"]
                        }
                    }
                }
            };

            const options = {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(payload)
            };

            const response = await fetchWithRetry(apiUrl, options);
            const result = await response.json();

            const candidate = result.candidates?.[0];
            if (!candidate || !candidate.content?.parts?.[0]?.text) {
                // If this fails, we don't throw, we just log and render a message
                console.warn("LLM failed to generate ingredient descriptions.");
                renderIngredientDescriptions([]);
                return;
            }

            const jsonString = candidate.content.parts[0].text;
            let descriptions = [];
           
            try {
                descriptions = JSON.parse(jsonString);
            } catch (e) {
                console.error("Failed to parse JSON response:", jsonString);
                renderIngredientDescriptions([]);
                return;
            }

            renderIngredientDescriptions(descriptions);
        };

        const renderIngredientDescriptions = (descriptions) => {
            const container = document.getElementById('ingredientDescriptions');
            container.innerHTML = ''; // Clear previous results

            if (!Array.isArray(descriptions) || descriptions.length === 0) {
                container.innerHTML = `<p class="text-gray-500">Could not generate ingredient descriptions. Please try different ingredient names.</p>`;
                return;
            }

            descriptions.forEach(item => {
                const div = document.createElement('div');
                div.className = "p-3 bg-light-blue rounded-lg border border-primary-blue/30 shadow-sm";
                div.innerHTML = `
                    <p class="font-bold text-gray-800">${item.ingredientName}:</p>
                    <p class="text-sm text-gray-700 mt-1">${item.simpleDescription}</p>
                `;
                container.appendChild(div);
            });
        };
       
        /**
         * Task 3: FSSAI Compliance Summary (LLM Call using uploaded documents)
         */
        const analyzeFSSAICompliance = async (totalResults, per100gData) => {
            const container = document.getElementById('fssaiComplianceSummary');
            container.innerHTML = '<div class="text-center text-primary-blue"><div class="animate-spin inline-block w-4 h-4 border-2 border-primary-blue border-t-transparent rounded-full mr-2"></div> Checking FSSAI documents...</div>';

            const sodiumPer100g = per100gData.sodium;
            const fatPer100g = per100gData.fat;
            const sugarPer100g = per100gData.sugar;
            const energyPer100g = per100gData.energy;

            // Providing the LLM with all necessary context from the input data
            const userQuery = `Analyze the following nutritional values (per 100g) against the FSSAI regulations provided in the documents. Focus on general standards for processed/packaged foods, especially regarding nutrient limits and front-of-package (FOP) labeling criteria for excess sugar, fat, and sodium, as detailed in the uploaded documents:
- Energy (kcal): ${energyPer100g}
- Total Fat (g): ${fatPer100g}
- Total Sugar (g): ${sugarPer100g}
- Sodium (mg): ${sodiumPer100g}

Provide a concise, single-paragraph summary of whether these values trigger any specific FSSAI warning criteria for **general packaged food** identified in the documents (like FOP labels). If an exact numerical standard for FOP warning criteria is not explicitly found, explain what the documents require for **nutritional information display** (Chapter 4 of the Labelling Regulations) based on the document context. Do not use external knowledge.`;
           
            const systemPrompt = "You are a regulatory compliance specialist. Your response must be grounded solely in the provided FSSAI documents. Explain the compliance status for the given nutritional values (per 100g) in a single, easy-to-read paragraph. Focus on FOP labeling or mandatory nutrient declaration requirements.";

            const payload = {
                contents: [{ parts: [{ text: userQuery }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] },
                tools: [{ "google_search": {} }], // Use search tool to access the documents
            };

            const options = {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(payload)
            };

            try {
                const response = await fetchWithRetry(apiUrl, options);
                const result = await response.json();

                const text = result.candidates?.[0]?.content?.parts?.[0]?.text || "Could not perform detailed FSSAI compliance check against the documents. The LLM response was empty or malformed.";

                container.innerHTML = `<p class="text-gray-700">${text}</p>`;

            } catch (e) {
                container.innerHTML = `<p class="text-red-600">Failed to analyze FSSAI documents: ${e.message}</p>`;
            }
        };

        // Initial setup for Lucide Icons
        window.onload = () => {
            lucide.createIcons();
        };

    </script>
</body>
</html>
