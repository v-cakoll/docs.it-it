---
title:
- TITOLO ARTICOLO
description: ''
author:
- GITHUB USERNAME
ms.author:
- MICROSOFT ALIAS OF INTERNAL OWNER
ms.date:
- CREATION/UPDATE DATE - mm/dd/yyyy
ms.topic:
- TOPIC TYPE
ms.prod:
- PRODUCT VALUE
helpviewer_keywords:
- OFFLINE BOOK INDEX ENTRIES
ms.openlocfilehash: e6c912f5ff9590f3b8cbb0f7e3f88e08fa9dd556
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106906"
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="e9e79-102">Modello Markdown e metadati</span><span class="sxs-lookup"><span data-stu-id="e9e79-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="e9e79-103">Il modello di dotnet/docs contiene esempi di sintassi di Markdown, nonché indicazioni su come impostare i metadati.</span><span class="sxs-lookup"><span data-stu-id="e9e79-103">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="e9e79-104">Per esaminarne la maggior parte, è necessario visualizzare sia il [Markdown non elaborato](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) che la [visualizzazione sottoposta a rendering](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (ad esempio, il Markdown non elaborato mostra il blocco dei metadati, che non è visibile nella visualizzazione sottoposta a rendering).</span><span class="sxs-lookup"><span data-stu-id="e9e79-104">To get the most of it, you must view both the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) and the [rendered view](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (for instance, the raw Markdown shows the metadata block, while the rendered view does not).</span></span>

<span data-ttu-id="e9e79-105">Quando si crea un file Markdown, è necessario copiare il modello in un nuovo file, compilare i metadati come specificato di seguito, impostare l'intestazione H1 sopra il titolo dell'articolo ed eliminare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="e9e79-105">When creating a Markdown file, you should copy this template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span>

## <a name="metadata"></a><span data-ttu-id="e9e79-106">Metadati</span><span class="sxs-lookup"><span data-stu-id="e9e79-106">Metadata</span></span>

<span data-ttu-id="e9e79-107">Il blocco di metadati completo è nella parte superiore (in formato [Markdown non elaborato](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), suddiviso in campi obbligatori e facoltativi.</span><span class="sxs-lookup"><span data-stu-id="e9e79-107">The full metadata block is above (in the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), divided into required fields and optional fields.</span></span> <span data-ttu-id="e9e79-108">Alcune note importanti:</span><span class="sxs-lookup"><span data-stu-id="e9e79-108">Some key notes:</span></span>

- <span data-ttu-id="e9e79-109">È **necessario** includere uno spazio tra i due punti (:) e il valore di un elemento di metadati.</span><span class="sxs-lookup"><span data-stu-id="e9e79-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="e9e79-110">Se a un elemento di metadati facoltativo non è associato un valore, impostare l'elemento come commento con un # o rimuoverlo (non lasciarlo vuoto o usare "na").</span><span class="sxs-lookup"><span data-stu-id="e9e79-110">If an optional metadata element doesn't have a value, comment out the element with a # or remove it (don't leave it blank or use "na").</span></span> <span data-ttu-id="e9e79-111">Se si aggiunge un valore a un elemento impostato come commento, assicurarsi di rimuovere il simbolo #.</span><span class="sxs-lookup"><span data-stu-id="e9e79-111">If you're adding a value to an element that was commented out, be sure to remove the #.</span></span>
- <span data-ttu-id="e9e79-112">La presenza dei due punti in un valore (ad esempio, un titolo) causa l'interruzione del parser dei metadati.</span><span class="sxs-lookup"><span data-stu-id="e9e79-112">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="e9e79-113">In questo caso, racchiudere il titolo tra virgolette doppie (ad esempio, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="e9e79-113">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="e9e79-114">**title**: viene visualizzato nei risultati del motore di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e9e79-114">**title**: Appears in search engine results.</span></span> <span data-ttu-id="e9e79-115">Il titolo non deve essere identico al titolo nell'intestazione H1 e può contenere al massimo 60 caratteri.</span><span class="sxs-lookup"><span data-stu-id="e9e79-115">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="e9e79-116">**description**: riepiloga il contenuto dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="e9e79-116">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="e9e79-117">In genere, viene visualizzato nella pagina dei risultati della ricerca ma non viene usato per classificare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e9e79-117">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="e9e79-118">La lunghezza deve essere inclusa tra 115 e 145 caratteri, spazi inclusi.</span><span class="sxs-lookup"><span data-stu-id="e9e79-118">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="e9e79-119">**author** e **ms.author**: il campo dell'autore deve contenere il **nome utente GitHub** dell'autore, non il relativo alias.</span><span class="sxs-lookup"><span data-stu-id="e9e79-119">**author** and **ms.author**: The author field should contain the **GitHub username** of the author, not his/her alias.</span></span>  <span data-ttu-id="e9e79-120">Il campo **ms.author** deve contenere invece un alias Microsoft e indica la persona responsabile della gestione dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="e9e79-120">The **ms.author** field, on the other hand, should contain a Microsoft alias and indicates the person responsible for maintaining the article.</span></span>
- <span data-ttu-id="e9e79-121">**ms.topic**: tipo di argomento.</span><span class="sxs-lookup"><span data-stu-id="e9e79-121">**ms.topic**: The topic type.</span></span> <span data-ttu-id="e9e79-122">Il valore più comune è `conceptual` e viene impostato a livello globale.</span><span class="sxs-lookup"><span data-stu-id="e9e79-122">The most common value is `conceptual` and is set at a global level.</span></span> <span data-ttu-id="e9e79-123">Altri valori comunemente usati sono `tutorial`, `overview` e `reference`.</span><span class="sxs-lookup"><span data-stu-id="e9e79-123">Other common values used are `tutorial`, `overview`, and `reference`.</span></span>
- <span data-ttu-id="e9e79-124">**ms.devlang** definisce il filtro linguaggio visualizzato per l'argomento.</span><span class="sxs-lookup"><span data-stu-id="e9e79-124">**ms.devlang** defines the language filter displayed for the topic.</span></span> <span data-ttu-id="e9e79-125">È possibile visualizzare un elenco dei valori supportati nella sezione [Linguaggi supportati](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="e9e79-125">You can see a list of the supported values in the [Supported languages](#supported-languages) section.</span></span> <span data-ttu-id="e9e79-126">Deve essere impostato solo se nell'argomento è presente più di un linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="e9e79-126">Only needs to be set when there's more than one programming language covered in the topic.</span></span> <span data-ttu-id="e9e79-127">Nei contenuti trattati, per questo valore vengono generalmente usati solo `csharp`, `vb`, `fsharp` e `cpp`.</span><span class="sxs-lookup"><span data-stu-id="e9e79-127">Typically, we only use `csharp`, `vb`, `fsharp`, and `cpp` for this value in our content.</span></span>
- <span data-ttu-id="e9e79-128">**ms.prod**: identificazione del prodotto usata per scopi di business intelligence.</span><span class="sxs-lookup"><span data-stu-id="e9e79-128">**ms.prod**: Product identification used for BI purposes.</span></span> <span data-ttu-id="e9e79-129">In genere, viene impostato a livello globale e non viene quindi visualizzato nel blocco di metadati di ogni articolo.</span><span class="sxs-lookup"><span data-stu-id="e9e79-129">They're usually set at a global level, so they don't usually appear in the metadata block of each article.</span></span>
- <span data-ttu-id="e9e79-130">**ms.technology**: classificazione di business intelligence aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="e9e79-130">**ms.technology**: Additional BI classification.</span></span> <span data-ttu-id="e9e79-131">Alcuni dei valori supportati sono: `devlang-csharp` per gli argomenti su C#, `devlang-fsharp` per gli argomenti su F# e `devlang-visual-basic` per gli argomenti su VB.</span><span class="sxs-lookup"><span data-stu-id="e9e79-131">Some of the supported values are: `devlang-csharp` for C# topics, `devlang-fsharp` for F# topics, and `devlang-visual-basic` for VB topics.</span></span> <span data-ttu-id="e9e79-132">Per le altre guide, i valori sono diversi ed è quindi opportuno chiedere al membro del team per informazioni in proposito.</span><span class="sxs-lookup"><span data-stu-id="e9e79-132">For other guides, the values will vary, so ask a member of the team for guidance.</span></span>
- <span data-ttu-id="e9e79-133">**ms.date**: data nel formato MM/gg/aaaa.</span><span class="sxs-lookup"><span data-stu-id="e9e79-133">**ms.date**: A date in the format MM/DD/YYYY.</span></span> <span data-ttu-id="e9e79-134">Viene visualizzata nella pagina pubblicata per indicare l'ultima volta in cui l'articolo è stato modificato in modo sostanziale o garantito "aggiornato" (l'articolo è stato esaminato e considerato aggiornato).</span><span class="sxs-lookup"><span data-stu-id="e9e79-134">Displayed on the published page to indicate the last time the article was substantially edited or guaranteed "fresh" (that is, the article was reviewed and considered up-to-date).</span></span>
- <span data-ttu-id="e9e79-135">**helpviewer_keywords**: voci usate per l'indice dei libri offline (funzionalità di Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="e9e79-135">**helpviewer_keywords**: Entries are used for the offline books index (functionality in Visual Studio).</span></span>
- <span data-ttu-id="e9e79-136">**f1_keywords**: connette l'articolo al tasto F1 (funzionalità di Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="e9e79-136">**f1_keywords**: Connects the article to the F1 key (functionality in Visual Studio).</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="e9e79-137">Markdown di base, GFM e caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="e9e79-137">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="e9e79-138">Sono supportati sia Markdown di base che GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="e9e79-138">All basic and GitHub Flavored Markdown (GFM) is supported.</span></span> <span data-ttu-id="e9e79-139">Per altre informazioni su questi elementi, vedere:</span><span class="sxs-lookup"><span data-stu-id="e9e79-139">For more information on these, see:</span></span>

- [<span data-ttu-id="e9e79-140">Sintassi Markdown di base</span><span class="sxs-lookup"><span data-stu-id="e9e79-140">Baseline Markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="e9e79-141">Documentazione di GFM</span><span class="sxs-lookup"><span data-stu-id="e9e79-141">GFM documentation</span></span>](https://guides.github.com/features/mastering-markdown)

<span data-ttu-id="e9e79-142">Markdown usa caratteri speciali, ad esempio \*, \` e \#, per la formattazione.</span><span class="sxs-lookup"><span data-stu-id="e9e79-142">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="e9e79-143">Se si vuole includere uno di questi caratteri nel contenuto, è necessario eseguire una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="e9e79-143">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="e9e79-144">Inserire una barra rovesciata prima del carattere speciale come "escape" (ad esempio, `\*` per \*)</span><span class="sxs-lookup"><span data-stu-id="e9e79-144">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="e9e79-145">Usare il [codice entità HTML](https://www.ascii.cl/htmlcodes.htm) per il carattere (ad esempio, `&#42;` per &#42;).</span><span class="sxs-lookup"><span data-stu-id="e9e79-145">Use the [HTML entity code](https://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-name"></a><span data-ttu-id="e9e79-146">Nome file</span><span class="sxs-lookup"><span data-stu-id="e9e79-146">File name</span></span>

<span data-ttu-id="e9e79-147">Per i nomi di file vengono usate le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9e79-147">File names use the following rules:</span></span>

- <span data-ttu-id="e9e79-148">Devono contenere solo lettere minuscole, numeri e trattini.</span><span class="sxs-lookup"><span data-stu-id="e9e79-148">Contain only lowercase letters, numbers, and hyphens.</span></span>
- <span data-ttu-id="e9e79-149">Non possono contenere spazi o caratteri di punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="e9e79-149">No spaces or punctuation characters.</span></span> <span data-ttu-id="e9e79-150">Usare i trattini per separare le parole e i numeri nel nome del file.</span><span class="sxs-lookup"><span data-stu-id="e9e79-150">Use the hyphens to separate words and numbers in the file name.</span></span>
- <span data-ttu-id="e9e79-151">Usare verbi di azione specifici, ad esempio sviluppare, acquistare, compilare, risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="e9e79-151">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="e9e79-152">Evitare i sostantivi.</span><span class="sxs-lookup"><span data-stu-id="e9e79-152">No -ing words.</span></span>
- <span data-ttu-id="e9e79-153">Non includere parole brevi, come un, e, il, in, o e così via.</span><span class="sxs-lookup"><span data-stu-id="e9e79-153">No small words - don't include a, and, the, in, or, etc.</span></span>
- <span data-ttu-id="e9e79-154">Usare il formato Markdown e l'estensione di file md.</span><span class="sxs-lookup"><span data-stu-id="e9e79-154">Must be in Markdown and use the .md file extension.</span></span>
- <span data-ttu-id="e9e79-155">Mantenere i nomi di file relativamente brevi.</span><span class="sxs-lookup"><span data-stu-id="e9e79-155">Keep file names reasonably short.</span></span> <span data-ttu-id="e9e79-156">Fanno parte dell'URL degli articoli.</span><span class="sxs-lookup"><span data-stu-id="e9e79-156">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="e9e79-157">Intestazioni</span><span class="sxs-lookup"><span data-stu-id="e9e79-157">Headings</span></span>

<span data-ttu-id="e9e79-158">Usare l'iniziale maiuscola solo per la prima parola.</span><span class="sxs-lookup"><span data-stu-id="e9e79-158">Use sentence-style capitalization.</span></span> <span data-ttu-id="e9e79-159">Scrivere sempre in maiuscolo:</span><span class="sxs-lookup"><span data-stu-id="e9e79-159">Always capitalize:</span></span>

- <span data-ttu-id="e9e79-160">La prima parola di un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="e9e79-160">The first word of a heading.</span></span>
- <span data-ttu-id="e9e79-161">La parola che segue i due punti in un titolo o un'intestazione (ad esempio, "Procedura: Ordinare una matrice").</span><span class="sxs-lookup"><span data-stu-id="e9e79-161">The word following a colon in a title or heading (for example, "How to: Sort an array").</span></span>

<span data-ttu-id="e9e79-162">È necessario creare le intestazioni in stile atx, ovvero usare 1-6 simboli di cancelletto (#) all'inizio della riga per indicare un'intestazione, corrispondenti ai livelli delle intestazioni HTML da H1 a H6.</span><span class="sxs-lookup"><span data-stu-id="e9e79-162">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="e9e79-163">Alcuni esempi di intestazioni di primo e secondo livello sono stati usati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e9e79-163">Examples of first- and second-level headers are used above.</span></span>

<span data-ttu-id="e9e79-164">Nell'argomento **deve** essere presente una sola intestazione di primo livello (H1), che verrà visualizzata come titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="e9e79-164">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="e9e79-165">Se l'intestazione termina con un carattere `#`, è necessario aggiungere un ulteriore carattere `#` alla fine per garantire che il rendering del titolo venga eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e9e79-165">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="e9e79-166">Ad esempio `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="e9e79-166">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="e9e79-167">Le intestazioni di secondo livello verranno usate per generare il sommario della pagina, visualizzato nella sezione "Contenuto dell'articolo" sotto il titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="e9e79-167">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="e9e79-168">Intestazione di terzo livello</span><span class="sxs-lookup"><span data-stu-id="e9e79-168">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="e9e79-169">Intestazione di quarto livello</span><span class="sxs-lookup"><span data-stu-id="e9e79-169">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="e9e79-170">Intestazione di quinto livello</span><span class="sxs-lookup"><span data-stu-id="e9e79-170">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="e9e79-171">Intestazione di sesto livello</span><span class="sxs-lookup"><span data-stu-id="e9e79-171">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="e9e79-172">Stile del testo</span><span class="sxs-lookup"><span data-stu-id="e9e79-172">Text styling</span></span>

<span data-ttu-id="e9e79-173">*Corsivo*: da usare per file, cartelle, percorsi (posizionare gli elementi lunghi su una riga distinta), nuovi termini.</span><span class="sxs-lookup"><span data-stu-id="e9e79-173">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="e9e79-174">**Grassetto**: da usare per gli elementi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="e9e79-174">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="e9e79-175">`Code` usarlo per il codice inline, le parole chiave del linguaggio, i nomi di pacchetti NuGet, i comandi della riga di comando, i nomi di tabella e colonna del database e gli URL sui quali non è possibile fare clic.</span><span class="sxs-lookup"><span data-stu-id="e9e79-175">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="e9e79-176">Collegamenti</span><span class="sxs-lookup"><span data-stu-id="e9e79-176">Links</span></span>

### <a name="internal-links"></a><span data-ttu-id="e9e79-177">Collegamenti interni</span><span class="sxs-lookup"><span data-stu-id="e9e79-177">Internal Links</span></span>

<span data-ttu-id="e9e79-178">Per creare un collegamento a un'intestazione nello stesso file Markdown (anche denominato collegamento di ancoraggio), è necessario individuare l'ID dell'intestazione da collegare.</span><span class="sxs-lookup"><span data-stu-id="e9e79-178">To link to a header in the same Markdown file (also known as anchor links), you'll need to find out the id of the header you're trying to link to.</span></span> <span data-ttu-id="e9e79-179">Per verificare l'ID, visualizzare l'origine dell'articolo sottoposto a rendering, trovare l'ID dell'intestazione (ad esempio, `id="blockquote"`) e specificare il collegamento usando il simbolo # e l'ID (ad esempio, `#blockquote`).</span><span class="sxs-lookup"><span data-stu-id="e9e79-179">To confirm the ID, view the source of the rendered article, find the id of the header (for example, `id="blockquote"`), and link using # + id (for example, `#blockquote`).</span></span>
<span data-ttu-id="e9e79-180">L'ID viene generato automaticamente in base al testo dell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="e9e79-180">The id is auto-generated based on the header text.</span></span> <span data-ttu-id="e9e79-181">Ad esempio, per una sezione univoca denominata `## Step 2`, l'ID sarà simile a `id="step-2"`.</span><span class="sxs-lookup"><span data-stu-id="e9e79-181">So, for example, given a unique section named `## Step 2`, the id would look like this `id="step-2"`.</span></span>

- <span data-ttu-id="e9e79-182">Esempio: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produce [Dichiara blocchi inline con un identificatore di lingua](#inline-code-blocks-with-language-identifier).</span><span class="sxs-lookup"><span data-stu-id="e9e79-182">Example: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produces [Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier).</span></span>

<span data-ttu-id="e9e79-183">Per creare un collegamento a un file Markdown nello stesso repository, usare [collegamenti relativi](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), includendo "md" alla fine del nome del file.</span><span class="sxs-lookup"><span data-stu-id="e9e79-183">To link to a Markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), including the ".md" at the end of the filename.</span></span>

- <span data-ttu-id="e9e79-184">Esempio: `[Readme file](../README.md)` produce [File leggimi](../README.md).</span><span class="sxs-lookup"><span data-stu-id="e9e79-184">Example: `[Readme file](../README.md)` produces [Readme file](../README.md).</span></span> <span data-ttu-id="e9e79-185">Questi valori distinguono tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="e9e79-185">(Note that links are case-sensitive.)</span></span>
- <span data-ttu-id="e9e79-186">Esempio: `[Welcome to .NET](../docs/welcome.md)` produce [Introduzione a .NET](../docs/welcome.md).</span><span class="sxs-lookup"><span data-stu-id="e9e79-186">Example: `[Welcome to .NET](../docs/welcome.md)` produces [Welcome to .NET](../docs/welcome.md).</span></span>

<span data-ttu-id="e9e79-187">Per creare un collegamento a un'intestazione in un file Markdown nello stesso repository, usare il collegamento relativo e il collegamento con hashtag.</span><span class="sxs-lookup"><span data-stu-id="e9e79-187">To link to a header in a Markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="e9e79-188">Esempio: `[.NET Community](../docs/welcome.md#open-source)` produce [Community .NET](../docs/welcome.md#open-source).</span><span class="sxs-lookup"><span data-stu-id="e9e79-188">Example: `[.NET Community](../docs/welcome.md#open-source)` produces [.NET Community](../docs/welcome.md#open-source).</span></span>

<span data-ttu-id="e9e79-189">Nella maggior parte dei casi si usano collegamenti relativi e si sconsiglia l'uso di `~/` nei collegamenti, perché i collegamenti relativi vengono risolti nell'origine in GitHub.</span><span class="sxs-lookup"><span data-stu-id="e9e79-189">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="e9e79-190">Tuttavia quando si definisce il collegamento a un file in un repository dipendente, viene usato il carattere `~/` per fornire il percorso.</span><span class="sxs-lookup"><span data-stu-id="e9e79-190">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="e9e79-191">Dato che i file nel repository dipendente si trovano in una posizione diversa in GitHub, i collegamenti non vengono risolti correttamente con collegamenti relativi, indipendentemente da come sono stati scritti.</span><span class="sxs-lookup"><span data-stu-id="e9e79-191">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>

<span data-ttu-id="e9e79-192">La specifica del linguaggio C# e la specifica del linguaggio Visual Basic sono incluse nei documenti .NET mediante l'aggiunta dell'origine dai repository del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="e9e79-192">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="e9e79-193">Le origini di markdown vengono gestite nei repository [csharplang](https://github.com/dotnet/csharplang) e [visual basic](https://github.com/dotnet/vblang).</span><span class="sxs-lookup"><span data-stu-id="e9e79-193">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [visual basic](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="e9e79-194">I collegamenti a una specifica devono fare riferimento alle directory di origine che includono le specifiche corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e9e79-194">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="e9e79-195">Per C# la directory è **~/_csharplang/spec** e per VB la directory è **~/_vblang/spec**.</span><span class="sxs-lookup"><span data-stu-id="e9e79-195">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="e9e79-196">Esempio: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` genera [Espressioni di query C#](~/_csharplang/spec/expressions.md#query-expressions).</span><span class="sxs-lookup"><span data-stu-id="e9e79-196">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` produces [C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions).</span></span>

### <a name="external-links"></a><span data-ttu-id="e9e79-197">Collegamenti esterni</span><span class="sxs-lookup"><span data-stu-id="e9e79-197">External Links</span></span>

<span data-ttu-id="e9e79-198">Per creare un collegamento a un file esterno, usare l'URL completo come collegamento.</span><span class="sxs-lookup"><span data-stu-id="e9e79-198">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="e9e79-199">Esempio: `[GitHub](https://www.github.com)` genera [GitHub](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="e9e79-199">Example: `[GitHub](https://www.github.com)` produces [GitHub](https://www.github.com).</span></span>

<span data-ttu-id="e9e79-200">Se un file Markdown contiene un URL, questo verrà trasformato in un collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="e9e79-200">If a URL appears in a Markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="e9e79-201">Esempio: `<https://www.github.com>` genera <https://www.github.com>.</span><span class="sxs-lookup"><span data-stu-id="e9e79-201">Example: `<https://www.github.com>` produces <https://www.github.com>.</span></span>

<span data-ttu-id="e9e79-202">Preferire il protocollo `https` per i collegamenti esterni.</span><span class="sxs-lookup"><span data-stu-id="e9e79-202">Prefer the `https` protocol for external links.</span></span> <span data-ttu-id="e9e79-203">Usare i collegamenti `http` solo per i siti che non supportano `https`.</span><span class="sxs-lookup"><span data-stu-id="e9e79-203">Only use `http` links for sites that do not support `https`.</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="e9e79-204">Collegamenti ad API</span><span class="sxs-lookup"><span data-stu-id="e9e79-204">Links to APIs</span></span>

<span data-ttu-id="e9e79-205">Il sistema di compilazione dispone di alcune estensioni che consentono di collegare API .NET senza che sia necessario usare collegamenti esterni.</span><span class="sxs-lookup"><span data-stu-id="e9e79-205">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span>
<span data-ttu-id="e9e79-206">Quando si crea un collegamento a un'API, è possibile usare il relativo identificatore univoco (UID), che viene generato automaticamente dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="e9e79-206">When linking to an API, you can use its unique identifier (UID) that is auto-generated from the source code.</span></span>

<span data-ttu-id="e9e79-207">L'UID equivale al nome completo di tipo e membro.</span><span class="sxs-lookup"><span data-stu-id="e9e79-207">The UID equates to the fully qualified type and member name.</span></span>

<span data-ttu-id="e9e79-208">Se si aggiunge \* (o %2A) dopo l'UID, il collegamento rappresenta la pagina di overload e non un'API specifica.</span><span class="sxs-lookup"><span data-stu-id="e9e79-208">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="e9e79-209">È ad esempio possibile usare questa opzione per creare un collegamento alla pagina [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) in modo generico anziché un overload specifico come [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span><span class="sxs-lookup"><span data-stu-id="e9e79-209">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="e9e79-210">È anche possibile usare \* per il collegamento a una pagina membro quando il membro non è in overload; in questo modo, è possibile evitare di includere l'elenco di parametri nell'UID.</span><span class="sxs-lookup"><span data-stu-id="e9e79-210">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="e9e79-211">Per il collegamento all'overload di un metodo specifico, è necessario includere il nome del tipo completo di ciascun parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="e9e79-211">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="e9e79-212">Ad esempio, \<xref:System.DateTime.ToString> definisce il collegamento al metodo senza parametri [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString), mentre \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> definisce il collegamento al metodo [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).</span><span class="sxs-lookup"><span data-stu-id="e9e79-212">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span> <span data-ttu-id="e9e79-213">È possibile trovare gli UID di un particolare membro di overload in `https://xref.docs.microsoft.com/autocomplete`.</span><span class="sxs-lookup"><span data-stu-id="e9e79-213">You can find the UIDs of a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="e9e79-214">La stringa di query "?text= *\<type-member-name>* " identifica il tipo o il membro di cui si vogliono visualizzare gli UID.</span><span class="sxs-lookup"><span data-stu-id="e9e79-214">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="e9e79-215">Ad esempio, `https://xref.docs.microsoft.com/autocomplete?text=string.format` recupera gli overload di [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).</span><span class="sxs-lookup"><span data-stu-id="e9e79-215">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span>

<span data-ttu-id="e9e79-216">Per il collegamento a un tipo generico, ad esempio [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), usare il carattere \` (%60) seguito dal numero dei parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="e9e79-216">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="e9e79-217">Ad esempio, \<xref:System.Nullable%601> definisce il collegamento al tipo [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), mentre \<xref:System.Func%602> definisce il collegamento al delegato [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).</span><span class="sxs-lookup"><span data-stu-id="e9e79-217">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

<span data-ttu-id="e9e79-218">È possibile usare una delle sintassi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9e79-218">You can use one of the following syntax:</span></span>

1. <span data-ttu-id="e9e79-219">Collegamento automatico: `<xref:UID>` o `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="e9e79-219">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="e9e79-220">Il parametro di query `displayProperty` produce un testo di collegamento completo.</span><span class="sxs-lookup"><span data-stu-id="e9e79-220">The `displayProperty` query    parameter produces a fully qualified link text.</span></span> <span data-ttu-id="e9e79-221">Per impostazione predefinita, il testo del collegamento mostra solo il nome del membro o del tipo.</span><span class="sxs-lookup"><span data-stu-id="e9e79-221">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="e9e79-222">Collegamento Markdown:`[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="e9e79-222">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="e9e79-223">Può essere usato quando si vuole personalizzare il testo del collegamento visualizzato.</span><span class="sxs-lookup"><span data-stu-id="e9e79-223">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="e9e79-224">Esempi:</span><span class="sxs-lookup"><span data-stu-id="e9e79-224">Examples:</span></span>

- <span data-ttu-id="e9e79-225">`<xref:System.String>` viene visualizzato come [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="e9e79-225">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="e9e79-226">`<xref:System.String?displayProperty=nameWithType>` viene visualizzato come [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="e9e79-226">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="e9e79-227">`[String class](xref:System.String)` viene visualizzato come [String class](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="e9e79-227">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="e9e79-228">Per altre informazioni sull'uso di questa notazione, vedere la pagina relativa all'[uso di riferimenti incrociati](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span><span class="sxs-lookup"><span data-stu-id="e9e79-228">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="e9e79-229">Di seguito sono illustrati i due modi disponibili per trovare l'UID:</span><span class="sxs-lookup"><span data-stu-id="e9e79-229">There are two ways to find the UID:</span></span>

- <span data-ttu-id="e9e79-230">Visualizzare l'origine della pagina API a cui ci si vuole collegare e trovare il valore ms.assetid.</span><span class="sxs-lookup"><span data-stu-id="e9e79-230">View the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="e9e79-231">Nell'origine, tuttavia, non vengono visualizzati i singoli valori di overload.</span><span class="sxs-lookup"><span data-stu-id="e9e79-231">Note that individual overload values are not shown in the source.</span></span>
- <span data-ttu-id="e9e79-232">Usare lo strumento seguente per cercare gli UID: https://xref.docs.microsoft.com/autocomplete?text=tostring (sostituire ToString con parti del nome dell'API che si sta tentando di trovare).</span><span class="sxs-lookup"><span data-stu-id="e9e79-232">Use the following tool to search for UIDs: https://xref.docs.microsoft.com/autocomplete?text=tostring (replace tostring with parts of the API name you're trying to find).</span></span> <span data-ttu-id="e9e79-233">Lo strumento cerca il parametro di query `text` specificato in qualsiasi parte dell'UID.</span><span class="sxs-lookup"><span data-stu-id="e9e79-233">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="e9e79-234">Ad esempio è possibile cercare il nome membro (ToString), il nome membro parziale (ToStri), il tipo e il nome membro (Double.ToString) e così via.</span><span class="sxs-lookup"><span data-stu-id="e9e79-234">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="e9e79-235">Se l'UID contiene i caratteri speciali, \`, \# o \*, il valore dell'UID deve essere codificato in formato HTML, rispettivamente come `%60`, `%23` e `%2A`.</span><span class="sxs-lookup"><span data-stu-id="e9e79-235">When the UID contains the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="e9e79-236">A volte possono essere codificate anche le parentesi, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e9e79-236">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="e9e79-237">Esempi:</span><span class="sxs-lookup"><span data-stu-id="e9e79-237">Examples:</span></span>

- <span data-ttu-id="e9e79-238">System.Threading.Tasks.Task\`1 diventa `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="e9e79-238">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="e9e79-239">System.Exception.\#ctor diventa `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="e9e79-239">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="e9e79-240">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) diventa `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="e9e79-240">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

## <a name="lists"></a><span data-ttu-id="e9e79-241">Elenchi</span><span class="sxs-lookup"><span data-stu-id="e9e79-241">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="e9e79-242">Elenchi ordinati</span><span class="sxs-lookup"><span data-stu-id="e9e79-242">Ordered lists</span></span>

1. <span data-ttu-id="e9e79-243">This</span><span class="sxs-lookup"><span data-stu-id="e9e79-243">This</span></span>
1. <span data-ttu-id="e9e79-244">È</span><span class="sxs-lookup"><span data-stu-id="e9e79-244">Is</span></span>
1. <span data-ttu-id="e9e79-245">Un</span><span class="sxs-lookup"><span data-stu-id="e9e79-245">An</span></span>
1. <span data-ttu-id="e9e79-246">Ordered</span><span class="sxs-lookup"><span data-stu-id="e9e79-246">Ordered</span></span>
1. <span data-ttu-id="e9e79-247">Elenco</span><span class="sxs-lookup"><span data-stu-id="e9e79-247">List</span></span>

#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="e9e79-248">Elenco ordinato con un elenco incorporato</span><span class="sxs-lookup"><span data-stu-id="e9e79-248">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="e9e79-249">Questo</span><span class="sxs-lookup"><span data-stu-id="e9e79-249">Here</span></span>
1. <span data-ttu-id="e9e79-250">è</span><span class="sxs-lookup"><span data-stu-id="e9e79-250">comes</span></span>
1. <span data-ttu-id="e9e79-251">any</span><span class="sxs-lookup"><span data-stu-id="e9e79-251">an</span></span>
1. <span data-ttu-id="e9e79-252">incorporato</span><span class="sxs-lookup"><span data-stu-id="e9e79-252">embedded</span></span>
    1. <span data-ttu-id="e9e79-253">Miss Scarlett</span><span class="sxs-lookup"><span data-stu-id="e9e79-253">Miss Scarlett</span></span>
    1. <span data-ttu-id="e9e79-254">Professor Plum</span><span class="sxs-lookup"><span data-stu-id="e9e79-254">Professor Plum</span></span>
1. <span data-ttu-id="e9e79-255">ordered</span><span class="sxs-lookup"><span data-stu-id="e9e79-255">ordered</span></span>
1. <span data-ttu-id="e9e79-256">list</span><span class="sxs-lookup"><span data-stu-id="e9e79-256">list</span></span>

### <a name="unordered-lists"></a><span data-ttu-id="e9e79-257">Elenchi non ordinati</span><span class="sxs-lookup"><span data-stu-id="e9e79-257">Unordered Lists</span></span>

- <span data-ttu-id="e9e79-258">This</span><span class="sxs-lookup"><span data-stu-id="e9e79-258">This</span></span>
- <span data-ttu-id="e9e79-259">is</span><span class="sxs-lookup"><span data-stu-id="e9e79-259">is</span></span>
- <span data-ttu-id="e9e79-260">a</span><span class="sxs-lookup"><span data-stu-id="e9e79-260">a</span></span>
- <span data-ttu-id="e9e79-261">puntato</span><span class="sxs-lookup"><span data-stu-id="e9e79-261">bulleted</span></span>
- <span data-ttu-id="e9e79-262">list</span><span class="sxs-lookup"><span data-stu-id="e9e79-262">list</span></span>

#### <a name="unordered-list-with-an-embedded-list"></a><span data-ttu-id="e9e79-263">Elenco non ordinato con un elenco incorporato</span><span class="sxs-lookup"><span data-stu-id="e9e79-263">Unordered list with an embedded list</span></span>

- <span data-ttu-id="e9e79-264">This</span><span class="sxs-lookup"><span data-stu-id="e9e79-264">This</span></span>
- <span data-ttu-id="e9e79-265">puntato</span><span class="sxs-lookup"><span data-stu-id="e9e79-265">bulleted</span></span>
- <span data-ttu-id="e9e79-266">list</span><span class="sxs-lookup"><span data-stu-id="e9e79-266">list</span></span>
  - <span data-ttu-id="e9e79-267">Signora Pavone</span><span class="sxs-lookup"><span data-stu-id="e9e79-267">Mrs. Peacock</span></span>
  - <span data-ttu-id="e9e79-268">Dottor Verde</span><span class="sxs-lookup"><span data-stu-id="e9e79-268">Mr. Green</span></span>
- <span data-ttu-id="e9e79-269">contiene</span><span class="sxs-lookup"><span data-stu-id="e9e79-269">contains</span></span>
- <span data-ttu-id="e9e79-270">altro</span><span class="sxs-lookup"><span data-stu-id="e9e79-270">other</span></span>
  1. <span data-ttu-id="e9e79-271">Colonnello Mustard</span><span class="sxs-lookup"><span data-stu-id="e9e79-271">Colonel Mustard</span></span>
  1. <span data-ttu-id="e9e79-272">Signora Bianchi</span><span class="sxs-lookup"><span data-stu-id="e9e79-272">Mrs. White</span></span>
- <span data-ttu-id="e9e79-273">elenchi</span><span class="sxs-lookup"><span data-stu-id="e9e79-273">lists</span></span>

## <a name="horizontal-rule"></a><span data-ttu-id="e9e79-274">Righello orizzontale</span><span class="sxs-lookup"><span data-stu-id="e9e79-274">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="e9e79-275">Tabelle</span><span class="sxs-lookup"><span data-stu-id="e9e79-275">Tables</span></span>

| <span data-ttu-id="e9e79-276">Tabelle</span><span class="sxs-lookup"><span data-stu-id="e9e79-276">Tables</span></span>        | <span data-ttu-id="e9e79-277">Sono</span><span class="sxs-lookup"><span data-stu-id="e9e79-277">Are</span></span>           | <span data-ttu-id="e9e79-278">Comode</span><span class="sxs-lookup"><span data-stu-id="e9e79-278">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="e9e79-279">col 3 è</span><span class="sxs-lookup"><span data-stu-id="e9e79-279">col 3 is</span></span>      | <span data-ttu-id="e9e79-280">allineata a destra</span><span class="sxs-lookup"><span data-stu-id="e9e79-280">right-aligned</span></span> | <span data-ttu-id="e9e79-281">$1600</span><span class="sxs-lookup"><span data-stu-id="e9e79-281">$1600</span></span> |
| <span data-ttu-id="e9e79-282">col 2 è</span><span class="sxs-lookup"><span data-stu-id="e9e79-282">col 2 is</span></span>      | <span data-ttu-id="e9e79-283">centrata</span><span class="sxs-lookup"><span data-stu-id="e9e79-283">centered</span></span>      |   <span data-ttu-id="e9e79-284">$12</span><span class="sxs-lookup"><span data-stu-id="e9e79-284">$12</span></span> |
| <span data-ttu-id="e9e79-285">col 1 è predefinita</span><span class="sxs-lookup"><span data-stu-id="e9e79-285">col 1 is default</span></span> | <span data-ttu-id="e9e79-286">allineata a sinistra</span><span class="sxs-lookup"><span data-stu-id="e9e79-286">left-aligned</span></span>     |    <span data-ttu-id="e9e79-287">$1</span><span class="sxs-lookup"><span data-stu-id="e9e79-287">$1</span></span> |

<span data-ttu-id="e9e79-288">Per creare le tabelle più facilmente, è possibile usare uno [strumento generatore di tabelle Markdown](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="e9e79-288">You can use a [Markdown table generator tool](https://www.tablesgenerator.com/markdown_tables) to help creating them more easily.</span></span>

## <a name="code"></a><span data-ttu-id="e9e79-289">Codice</span><span class="sxs-lookup"><span data-stu-id="e9e79-289">Code</span></span>

<span data-ttu-id="e9e79-290">Il modo migliore per includere codice consiste nell'includere frammenti di codice da un esempio funzionante.</span><span class="sxs-lookup"><span data-stu-id="e9e79-290">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="e9e79-291">Creare l'esempio seguendo le istruzioni nella [guida alla creazione di contributi](../CONTRIBUTING.md#contributing-to-samples).</span><span class="sxs-lookup"><span data-stu-id="e9e79-291">Create your sample following the instructions in the [contributing guide](../CONTRIBUTING.md#contributing-to-samples).</span></span>

<span data-ttu-id="e9e79-292">È possibile includere il codice usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e9e79-292">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- <span data-ttu-id="e9e79-293">`-<language>` (*facoltativo* ma *consigliato*)</span><span class="sxs-lookup"><span data-stu-id="e9e79-293">`-<language>` (*optional* but *recommended*)</span></span>
  - <span data-ttu-id="e9e79-294">Linguaggio del frammento di codice al quale si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="e9e79-294">Language of the code snippet being referenced.</span></span> <span data-ttu-id="e9e79-295">Per un elenco completo dei valori supportati, vedere [Linguaggi supportate](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="e9e79-295">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

- <span data-ttu-id="e9e79-296">`<name>` (*facoltativo*)</span><span class="sxs-lookup"><span data-stu-id="e9e79-296">`<name>` (*optional*)</span></span>
  - <span data-ttu-id="e9e79-297">Nome del frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="e9e79-297">Name for the code snippet.</span></span> <span data-ttu-id="e9e79-298">Non deve avere alcun impatto sul file HTML di output ma può essere usato per rendere più leggibile l'origine del Markdown.</span><span class="sxs-lookup"><span data-stu-id="e9e79-298">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

- <span data-ttu-id="e9e79-299">`<pathToFile>` (*obbligatorio*)</span><span class="sxs-lookup"><span data-stu-id="e9e79-299">`<pathToFile>` (*mandatory*)</span></span>
  - <span data-ttu-id="e9e79-300">Percorso relativo nel file system che indica il file del frammento di codice a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="e9e79-300">Relative path in the file system that indicates the code snippet file to reference.</span></span>

- <span data-ttu-id="e9e79-301">`<queryoption>` e `<queryoptionvalue>` (*facoltativi*)</span><span class="sxs-lookup"><span data-stu-id="e9e79-301">`<queryoption>` and `<queryoptionvalue>` (*optional*)</span></span>
  - <span data-ttu-id="e9e79-302">Da usare insieme per specificare come deve essere recuperato il codice dal file:</span><span class="sxs-lookup"><span data-stu-id="e9e79-302">Used together to specify how the code should be retrieved from the file:</span></span>
    - <span data-ttu-id="e9e79-303">`#`:  `#L{startlinenumber}-L{endlinenumber}` (intervallo di righe) *o* `#{tagname}` (nome del tag).</span><span class="sxs-lookup"><span data-stu-id="e9e79-303">`#`:  `#L{startlinenumber}-L{endlinenumber}` (line range) *or* `#{tagname}` (tag name).</span></span>
    <span data-ttu-id="e9e79-304">L'uso dei numeri di riga è sconsigliato in quanto non sufficientemente affidabile.</span><span class="sxs-lookup"><span data-stu-id="e9e79-304">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="e9e79-305">Il nome del tag è il metodo preferibile per il riferimento ai frammenti di codice.</span><span class="sxs-lookup"><span data-stu-id="e9e79-305">Tag name is the preferred way of referencing code snippets.</span></span>
    - <span data-ttu-id="e9e79-306">`range`: `?range=1,3-5` Intervallo di righe.</span><span class="sxs-lookup"><span data-stu-id="e9e79-306">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="e9e79-307">Questo esempio include le righe 1, 3, 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="e9e79-307">This example includes lines 1, 3, 4, and 5.</span></span>
    - <span data-ttu-id="e9e79-308">`dedent`: `?dedent=8` Riduce il rientro delle righe di un numero di spazi, in questo caso 8.</span><span class="sxs-lookup"><span data-stu-id="e9e79-308">`dedent`: `?dedent=8` Dedents the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="e9e79-309">Questo valore può essere combinato con `range` e altre opzioni di query che consentono di selezionare un subset di righe di un file.</span><span class="sxs-lookup"><span data-stu-id="e9e79-309">This can be combined with the `range` and other query options that select a subset of the lines of a file.</span></span>
    - <span data-ttu-id="e9e79-310">`outdent`: `?outdent=8` Inverte il rientro delle righe di un numero di spazi, in questo caso 8.</span><span class="sxs-lookup"><span data-stu-id="e9e79-310">`outdent`: `?outdent=8` Reverses the indent of the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="e9e79-311">Questo valore può essere combinato con `range` e altre opzioni di query che consentono di selezionare un subset di righe di un file.</span><span class="sxs-lookup"><span data-stu-id="e9e79-311">This can be combined with `range` and other query options that select a subset of the lines of a file.</span></span>

<span data-ttu-id="e9e79-312">Se possibile, è sempre consigliabile usare l'opzione del nome del tag.</span><span class="sxs-lookup"><span data-stu-id="e9e79-312">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="e9e79-313">Il nome del tag è il nome di un'area o di un commento di codice nel formato `Snippettagname` presente nel codice di origine.</span><span class="sxs-lookup"><span data-stu-id="e9e79-313">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="e9e79-314">L'esempio seguente illustra come creare un riferimento al nome di tag `1`:</span><span class="sxs-lookup"><span data-stu-id="e9e79-314">The following example shows how to refer to the tag name `1`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

<span data-ttu-id="e9e79-315">È anche possibile vedere come sono strutturati i tag dei frammenti di codice in [questo file di origine](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span><span class="sxs-lookup"><span data-stu-id="e9e79-315">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span></span> <span data-ttu-id="e9e79-316">Per altri dettagli sulla rappresentazione dei nomi di tag nei file di origine dei frammenti di codice in base al linguaggio, vedere le [linee guida per DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="e9e79-316">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="e9e79-317">L'inclusione di frammenti di codice da programmi completi assicura che tutto il codice venga eseguito tramite il sistema di Integrazione continua.</span><span class="sxs-lookup"><span data-stu-id="e9e79-317">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="e9e79-318">Se tuttavia è necessario mostrare un elemento che causa errori di runtime o in fase di compilazione, è possibile usare i blocchi di codice inline.</span><span class="sxs-lookup"><span data-stu-id="e9e79-318">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

### <a name="inline-code-blocks-with-language-identifier"></a><span data-ttu-id="e9e79-319">Blocchi di codice inline con identificatore del linguaggio</span><span class="sxs-lookup"><span data-stu-id="e9e79-319">Inline code blocks with language identifier</span></span>

<span data-ttu-id="e9e79-320">Usare tre apici (\`\`\`) e un ID di linguaggio per applicare il codice a colori di uno specifico linguaggio a un blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="e9e79-320">Use three backticks (\`\`\`) + a language ID to apply language-specific color coding to a code block.</span></span> <span data-ttu-id="e9e79-321">Di seguito è riportato l'elenco dei linguaggi supportati, con l'etichetta Markdown per ogni ID di lingua.</span><span class="sxs-lookup"><span data-stu-id="e9e79-321">Here is the list of supported languages showing the markdown label for each language ID.</span></span>

#### <a name="supported-languages"></a><span data-ttu-id="e9e79-322">Lingue supportate</span><span class="sxs-lookup"><span data-stu-id="e9e79-322">Supported languages</span></span>

|<span data-ttu-id="e9e79-323">nome</span><span class="sxs-lookup"><span data-stu-id="e9e79-323">Name</span></span>|<span data-ttu-id="e9e79-324">Etichetta Markdown</span><span class="sxs-lookup"><span data-stu-id="e9e79-324">Markdown label</span></span>|
|-----|-------|
|<span data-ttu-id="e9e79-325">ASP.NET con C#</span><span class="sxs-lookup"><span data-stu-id="e9e79-325">ASP.NET with C#</span></span>|<span data-ttu-id="e9e79-326">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="e9e79-326">aspx-csharp</span></span>|
|<span data-ttu-id="e9e79-327">ASP.NET con VB</span><span class="sxs-lookup"><span data-stu-id="e9e79-327">ASP.NET with VB</span></span>|<span data-ttu-id="e9e79-328">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="e9e79-328">aspx-vb</span></span>|
|<span data-ttu-id="e9e79-329">Interfaccia della riga di comando di Azure</span><span class="sxs-lookup"><span data-stu-id="e9e79-329">Azure CLI</span></span>|<span data-ttu-id="e9e79-330">azurecli</span><span class="sxs-lookup"><span data-stu-id="e9e79-330">azurecli</span></span>|
|<span data-ttu-id="e9e79-331">AzCopy</span><span class="sxs-lookup"><span data-stu-id="e9e79-331">AzCopy</span></span>|<span data-ttu-id="e9e79-332">azcopy</span><span class="sxs-lookup"><span data-stu-id="e9e79-332">azcopy</span></span>|
|<span data-ttu-id="e9e79-333">C++</span><span class="sxs-lookup"><span data-stu-id="e9e79-333">C++</span></span>|<span data-ttu-id="e9e79-334">cpp</span><span class="sxs-lookup"><span data-stu-id="e9e79-334">cpp</span></span>|
|<span data-ttu-id="e9e79-335">C#</span><span class="sxs-lookup"><span data-stu-id="e9e79-335">C#</span></span>|<span data-ttu-id="e9e79-336">csharp</span><span class="sxs-lookup"><span data-stu-id="e9e79-336">csharp</span></span>|
|<span data-ttu-id="e9e79-337">C# nel browser</span><span class="sxs-lookup"><span data-stu-id="e9e79-337">C# in browser</span></span>|<span data-ttu-id="e9e79-338">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="e9e79-338">csharp-interactive</span></span>|
|<span data-ttu-id="e9e79-339">Console</span><span class="sxs-lookup"><span data-stu-id="e9e79-339">Console</span></span>|<span data-ttu-id="e9e79-340">console</span><span class="sxs-lookup"><span data-stu-id="e9e79-340">console</span></span>|
|<span data-ttu-id="e9e79-341">F#</span><span class="sxs-lookup"><span data-stu-id="e9e79-341">F#</span></span>|<span data-ttu-id="e9e79-342">fsharp</span><span class="sxs-lookup"><span data-stu-id="e9e79-342">fsharp</span></span>|
|<span data-ttu-id="e9e79-343">Java</span><span class="sxs-lookup"><span data-stu-id="e9e79-343">Java</span></span>|<span data-ttu-id="e9e79-344">java</span><span class="sxs-lookup"><span data-stu-id="e9e79-344">java</span></span>|
|<span data-ttu-id="e9e79-345">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e9e79-345">JavaScript</span></span>|<span data-ttu-id="e9e79-346">javascript</span><span class="sxs-lookup"><span data-stu-id="e9e79-346">javascript</span></span>|
|<span data-ttu-id="e9e79-347">JSON</span><span class="sxs-lookup"><span data-stu-id="e9e79-347">JSON</span></span>|<span data-ttu-id="e9e79-348">json</span><span class="sxs-lookup"><span data-stu-id="e9e79-348">json</span></span>|
|<span data-ttu-id="e9e79-349">NodeJS</span><span class="sxs-lookup"><span data-stu-id="e9e79-349">NodeJS</span></span>|<span data-ttu-id="e9e79-350">nodejs</span><span class="sxs-lookup"><span data-stu-id="e9e79-350">nodejs</span></span>|
|<span data-ttu-id="e9e79-351">Objective-C</span><span class="sxs-lookup"><span data-stu-id="e9e79-351">Objective-C</span></span>|<span data-ttu-id="e9e79-352">objc</span><span class="sxs-lookup"><span data-stu-id="e9e79-352">objc</span></span>|
|<span data-ttu-id="e9e79-353">PHP</span><span class="sxs-lookup"><span data-stu-id="e9e79-353">PHP</span></span>|<span data-ttu-id="e9e79-354">php</span><span class="sxs-lookup"><span data-stu-id="e9e79-354">php</span></span>|
|<span data-ttu-id="e9e79-355">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9e79-355">PowerShell</span></span>|<span data-ttu-id="e9e79-356">powershell</span><span class="sxs-lookup"><span data-stu-id="e9e79-356">powershell</span></span>|
|<span data-ttu-id="e9e79-357">Python</span><span class="sxs-lookup"><span data-stu-id="e9e79-357">Python</span></span>|<span data-ttu-id="e9e79-358">python</span><span class="sxs-lookup"><span data-stu-id="e9e79-358">python</span></span>|
|<span data-ttu-id="e9e79-359">Ruby</span><span class="sxs-lookup"><span data-stu-id="e9e79-359">Ruby</span></span>|<span data-ttu-id="e9e79-360">ruby</span><span class="sxs-lookup"><span data-stu-id="e9e79-360">ruby</span></span>|
|<span data-ttu-id="e9e79-361">SQL</span><span class="sxs-lookup"><span data-stu-id="e9e79-361">SQL</span></span>|<span data-ttu-id="e9e79-362">sql</span><span class="sxs-lookup"><span data-stu-id="e9e79-362">sql</span></span>|
|<span data-ttu-id="e9e79-363">Swift</span><span class="sxs-lookup"><span data-stu-id="e9e79-363">Swift</span></span>|<span data-ttu-id="e9e79-364">swift</span><span class="sxs-lookup"><span data-stu-id="e9e79-364">swift</span></span>|
|<span data-ttu-id="e9e79-365">VB</span><span class="sxs-lookup"><span data-stu-id="e9e79-365">VB</span></span>|<span data-ttu-id="e9e79-366">VB</span><span class="sxs-lookup"><span data-stu-id="e9e79-366">vb</span></span>|
|<span data-ttu-id="e9e79-367">XAML</span><span class="sxs-lookup"><span data-stu-id="e9e79-367">XAML</span></span>|<span data-ttu-id="e9e79-368">xaml</span><span class="sxs-lookup"><span data-stu-id="e9e79-368">xaml</span></span>|
|<span data-ttu-id="e9e79-369">XML</span><span class="sxs-lookup"><span data-stu-id="e9e79-369">XML</span></span>|<span data-ttu-id="e9e79-370">xml</span><span class="sxs-lookup"><span data-stu-id="e9e79-370">xml</span></span>|

<span data-ttu-id="e9e79-371">Il nome `csharp-interactive` specifica il linguaggio C# e la possibilità di eseguire gli esempi dal browser.</span><span class="sxs-lookup"><span data-stu-id="e9e79-371">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="e9e79-372">Questi frammenti vengono compilati ed eseguiti in un contenitore Docker e i risultati dell'esecuzione del programma vengono visualizzati nella finestra del browser dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e9e79-372">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

<span data-ttu-id="e9e79-373">Di seguito sono riportati esempi di blocchi di codice che usano gli ID linguaggio per C# (\`\`\`csharp), Python (\`\`\`python) e PowerShell (\`\`\`powershell).</span><span class="sxs-lookup"><span data-stu-id="e9e79-373">The following are examples of code blocks using the language IDs for C# (\`\`\`csharp), Python (\`\`\`python), and PowerShell (\`\`\`powershell).</span></span>

##### <a name="c9839"></a><span data-ttu-id="e9e79-374">C&#9839;</span><span class="sxs-lookup"><span data-stu-id="e9e79-374">C&#9839;</span></span>

```csharp
using System;
namespace HelloWorld
{
    class Hello
    {
        static void Main()
        {
            Console.WriteLine("Hello World!");

            // Keep the console window open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

#### <a name="python"></a><span data-ttu-id="e9e79-375">Python</span><span class="sxs-lookup"><span data-stu-id="e9e79-375">Python</span></span>

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a><span data-ttu-id="e9e79-376">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9e79-376">PowerShell</span></span>

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a><span data-ttu-id="e9e79-377">Blocco di codice generico</span><span class="sxs-lookup"><span data-stu-id="e9e79-377">Generic code block</span></span>

<span data-ttu-id="e9e79-378">Usare tre apici (&#96;&#96;&#96;) per la codifica di un blocco di codice generico.</span><span class="sxs-lookup"><span data-stu-id="e9e79-378">Use three backticks (&#96;&#96;&#96;) for generic code block coding.</span></span>

> <span data-ttu-id="e9e79-379">L'approccio consigliato è usare blocchi di codice con identificatori di linguaggio, come illustrato nella sezione precedente, per garantire la corretta evidenziazione della sintassi nel sito della documentazione.</span><span class="sxs-lookup"><span data-stu-id="e9e79-379">The recommended approach is to use code blocks with language identifiers as explained in the previous section to ensure the proper syntax highlighting in the documentation site.</span></span> <span data-ttu-id="e9e79-380">Usare blocchi di codice generico solo quando necessario.</span><span class="sxs-lookup"><span data-stu-id="e9e79-380">Use generic code blocks only when necessary.</span></span>

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a><span data-ttu-id="e9e79-381">Citazioni di paragrafi</span><span class="sxs-lookup"><span data-stu-id="e9e79-381">Blockquotes</span></span>

> <span data-ttu-id="e9e79-382">La siccità si protraeva ormai da dieci milioni di anni, e il regno delle terribili lucertole era finito da molto tempo.</span><span class="sxs-lookup"><span data-stu-id="e9e79-382">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="e9e79-383">Lì, sull'Equatore, nel continente che un giorno sarebbe stato chiamato Africa, la lotta per la vita aveva raggiunto un nuovo diapason di ferocia, e il vincitore ancora non si intravedeva.</span><span class="sxs-lookup"><span data-stu-id="e9e79-383">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="e9e79-384">In quella terra sterile e arida soltanto le creature piccole o fulminee o feroci potevano prosperare, o appena sperare di sopravvivere.</span><span class="sxs-lookup"><span data-stu-id="e9e79-384">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="e9e79-385">Immagini</span><span class="sxs-lookup"><span data-stu-id="e9e79-385">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="e9e79-386">Immagine statica o GIF animata</span><span class="sxs-lookup"><span data-stu-id="e9e79-386">Static Image or Animated gif</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![questo è il testo alternativo](../images/Logo_DotNet.png)

### <a name="linked-image"></a><span data-ttu-id="e9e79-388">Immagine collegata</span><span class="sxs-lookup"><span data-stu-id="e9e79-388">Linked Image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

<span data-ttu-id="e9e79-389">[![testo alternativo per l'immagine collegata](../images/Logo_DotNet.png)](https://dot.net)</span><span class="sxs-lookup"><span data-stu-id="e9e79-389">[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)</span></span>

## <a name="videos"></a><span data-ttu-id="e9e79-390">Video</span><span class="sxs-lookup"><span data-stu-id="e9e79-390">Videos</span></span>

<span data-ttu-id="e9e79-391">Attualmente è possibile incorporare video sia di Channel 9 che di YouTube con la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e9e79-391">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="e9e79-392">Channel 9</span><span class="sxs-lookup"><span data-stu-id="e9e79-392">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="e9e79-393">Per ottenere l'URL corretto del video, selezionare la scheda **Incorpora** sotto il fotogramma video e copiare l'URL dall'elemento `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="e9e79-393">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="e9e79-394">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e9e79-394">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="e9e79-395">YouTube</span><span class="sxs-lookup"><span data-stu-id="e9e79-395">YouTube</span></span>

<span data-ttu-id="e9e79-396">Per ottenere l'URL corretto del video, fare clic con il pulsante destro del mouse sul video, selezionare **Copia codice di incorporamento** e copiare l'URL dall'elemento `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="e9e79-396">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="e9e79-397">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e9e79-397">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="e9e79-398">Estensioni docs.microsoft</span><span class="sxs-lookup"><span data-stu-id="e9e79-398">docs.microsoft extensions</span></span>

<span data-ttu-id="e9e79-399">docs.microsoft fornisce alcune estensioni aggiuntive a GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="e9e79-399">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="alerts"></a><span data-ttu-id="e9e79-400">Avvisi</span><span class="sxs-lookup"><span data-stu-id="e9e79-400">Alerts</span></span>

<span data-ttu-id="e9e79-401">È importante usare gli stili di avviso seguenti, in modo che ne venga eseguito il rendering con lo stile appropriato nel sito della documentazione.</span><span class="sxs-lookup"><span data-stu-id="e9e79-401">It's important to use the following alert styles so they render with the proper style in the documentation site.</span></span> <span data-ttu-id="e9e79-402">Tuttavia, il motore di rendering in GitHub non li differenzia.</span><span class="sxs-lookup"><span data-stu-id="e9e79-402">However, the rendering engine on GitHub doesn't diferentiate them.</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="e9e79-403">Il rendering sarà simile al seguente: ![Stili di avviso](../images/alerts.png)</span><span class="sxs-lookup"><span data-stu-id="e9e79-403">And they'll render like this: ![Alert styles](../images/alerts.png)</span></span>

### <a name="includes"></a><span data-ttu-id="e9e79-404">Include</span><span class="sxs-lookup"><span data-stu-id="e9e79-404">Includes</span></span>

<span data-ttu-id="e9e79-405">È possibile incorporare il Markdown di un file in un altro usando un'inclusione.</span><span class="sxs-lookup"><span data-stu-id="e9e79-405">You can embed the Markdown of one file into another using an include.</span></span>

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a><span data-ttu-id="e9e79-406">Elenchi selezionati</span><span class="sxs-lookup"><span data-stu-id="e9e79-406">Checked lists</span></span>

<span data-ttu-id="e9e79-407">Per gli elenchi è disponibile uno stile personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e9e79-407">A custom style is available for lists.</span></span> <span data-ttu-id="e9e79-408">È possibile eseguire il rendering degli elenchi con segni di spunta verdi.</span><span class="sxs-lookup"><span data-stu-id="e9e79-408">You can render lists with green check marks.</span></span>

> [!div class="checklist"]
> - <span data-ttu-id="e9e79-409">Come creare un'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="e9e79-409">How to create a .NET Core app</span></span>
> - <span data-ttu-id="e9e79-410">Come aggiungere un riferimento al pacchetto Microsoft.XmlSerializer.Generator</span><span class="sxs-lookup"><span data-stu-id="e9e79-410">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="e9e79-411">Come modificare il file MyApp.cspro per aggiungere dipendenze</span><span class="sxs-lookup"><span data-stu-id="e9e79-411">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="e9e79-412">Come aggiungere una classe e un oggetto XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="e9e79-412">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="e9e79-413">Come compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="e9e79-413">How to build and run the application</span></span>

<span data-ttu-id="e9e79-414">È possibile vedere un esempio di elenchi selezionati in azione nella [documentazione di .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="e9e79-414">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="e9e79-415">Pulsanti</span><span class="sxs-lookup"><span data-stu-id="e9e79-415">Buttons</span></span>

> [!div class="button"]
> [<span data-ttu-id="e9e79-416">collegamenti con pulsanti</span><span class="sxs-lookup"><span data-stu-id="e9e79-416">button links</span></span>](../docs/core/index.md)

<span data-ttu-id="e9e79-417">È possibile vedere un esempio di pulsanti in azione nella [documentazione di Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e9e79-417">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="selectors"></a><span data-ttu-id="e9e79-418">Selettori</span><span class="sxs-lookup"><span data-stu-id="e9e79-418">Selectors</span></span>

> [!div class="op_single_selector"]
- [<span data-ttu-id="e9e79-419">macOS</span><span class="sxs-lookup"><span data-stu-id="e9e79-419">macOS</span></span>](../docs/core/tutorials/using-on-macos.md)
- [<span data-ttu-id="e9e79-420">Windows</span><span class="sxs-lookup"><span data-stu-id="e9e79-420">Windows</span></span>](../docs/core/tutorials/with-visual-studio.md)

<span data-ttu-id="e9e79-421">È possibile vedere un esempio di selettori in azione nella [documentazione di Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span><span class="sxs-lookup"><span data-stu-id="e9e79-421">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="e9e79-422">Procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="e9e79-422">Step-By-Steps</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e9e79-423">[Precedente](../docs/csharp/expression-trees-interpreting.md)
>[Successivo](../docs/csharp/expression-trees-translating.md)</span><span class="sxs-lookup"><span data-stu-id="e9e79-423">[Previous](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)</span></span>

<span data-ttu-id="e9e79-424">È possibile vedere un esempio di procedure dettagliate in azione nella [Guida di C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="e9e79-424">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
