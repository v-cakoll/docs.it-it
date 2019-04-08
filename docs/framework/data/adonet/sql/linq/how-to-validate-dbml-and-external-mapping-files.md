---
title: 'Procedura: Convalidare file di mapping esterni e DBML'
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: b01bcf98bba185b7a4b1802f470a585371980177
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078733"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="6d8f0-102">Procedura: Convalidare file di mapping esterni e DBML</span><span class="sxs-lookup"><span data-stu-id="6d8f0-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="6d8f0-103">I file di mapping esterno e i file con estensione dbml modificati devono essere convalidati in base alle rispettive definizioni dello schema.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="6d8f0-104">In questo argomento offre agli utenti di Visual Studio con i passaggi per implementare il processo di convalida.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-104">This topic provides Visual Studio users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="6d8f0-105">Per convalidare un file con estensione dbml o un file XML</span><span class="sxs-lookup"><span data-stu-id="6d8f0-105">To validate a .dbml or XML file</span></span>  
  
1.  <span data-ttu-id="6d8f0-106">In Visual Studio **File** dal menu **Open**, quindi fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="6d8f0-107">Nel **Apri File** finestra di dialogo, scegliere il. dbml o un file di mapping XML che si desidera convalidare.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="6d8f0-108">Aprire il file nei **Editor XML**.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-108">The file opens in the **XML Editor**.</span></span>  
  
3.  <span data-ttu-id="6d8f0-109">Fare doppio clic la finestra e quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-109">Right-click the window, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="6d8f0-110">Nel **delle proprietà** finestra, fare clic sui puntini di sospensione per il **schemi** proprietà.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="6d8f0-111">Il **schemi XML** verrà visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-111">The **XML Schemas** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="6d8f0-112">Notare la definizione dello schema adatta allo scopo.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    -   <span data-ttu-id="6d8f0-113">DbmlSchema.xsd è la definizione dello schema per la convalida di un file dbml.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="6d8f0-114">Per altre informazioni, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6d8f0-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="6d8f0-115">LinqToSqlMapping.xsd è la definizione dello schema per la convalida di un file di mapping XML esterno.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="6d8f0-116">Per altre informazioni, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="6d8f0-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6.  <span data-ttu-id="6d8f0-117">Nel **utilizzo** colonna della riga di definizione dello schema desiderata, fare clic per aprire la casella di riepilogo a discesa e quindi fare clic su **utilizzano questo schema**.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="6d8f0-118">Il file di definizione dello schema è ora associato al file di mapping DBML o XML.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="6d8f0-119">Assicurarsi che non siano selezionate altre definizioni dello schema.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-119">Make sure no other schema definitions are selected.</span></span>  
  
7.  <span data-ttu-id="6d8f0-120">Nel **View** menu, fare clic su **elenco errori**.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="6d8f0-121">Determinare se sono stati generati errori, avvisi o messaggi.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="6d8f0-122">In caso contrario, il file XML è valido per la definizione dello schema.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="6d8f0-123">Metodo alternativo per fornire la definizione dello schema</span><span class="sxs-lookup"><span data-stu-id="6d8f0-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="6d8f0-124">Se per qualche motivo il XSD appropriato file non viene visualizzato nei **schemi XML** nella finestra di dialogo è possibile scaricare il file con estensione XSD da un argomento della Guida.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="6d8f0-125">La procedura seguente consente di salvare il file scaricato in formato Unicode richiesto dall'Editor XML di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-125">The following steps help you save the downloaded file in the Unicode format required by the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="6d8f0-126">Per copiare un file di definizione dello schema da un argomento della Guida</span><span class="sxs-lookup"><span data-stu-id="6d8f0-126">To copy a schema definition file from a Help topic</span></span>  
  
1.  <span data-ttu-id="6d8f0-127">Individuare l'argomento della Guida che contiene la definizione dello schema descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    -   <span data-ttu-id="6d8f0-128">Per i file con estensione dbml, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6d8f0-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="6d8f0-129">Per i file di mapping esterno, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="6d8f0-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2.  <span data-ttu-id="6d8f0-130">Fare clic su **Copia codice** per copiare il file di codice negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="6d8f0-131">Avviare il Blocco note per creare un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-131">Start Notepad to create a new file.</span></span>  
  
4.  <span data-ttu-id="6d8f0-132">Incollare il codice dagli Appunti nel file del Blocco note.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5.  <span data-ttu-id="6d8f0-133">Nel blocco note **File** menu, fare clic su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6.  <span data-ttu-id="6d8f0-134">Nel **Encoding** , quindi selezionare **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6d8f0-135">Questa selezione assicura che il file di testo sia preceduto dal marcatore dell'ordine di byte Unicode 16 (`FFFE`).</span><span class="sxs-lookup"><span data-stu-id="6d8f0-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7.  <span data-ttu-id="6d8f0-136">Nel **nome del File** casella, creare un nome di file con estensione XSD.</span><span class="sxs-lookup"><span data-stu-id="6d8f0-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d8f0-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d8f0-137">See also</span></span>

- [<span data-ttu-id="6d8f0-138">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="6d8f0-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
