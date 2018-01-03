---
title: 'Procedura: convalidare file di mapping esterni e DBML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 9339176cbc6a72d940e3fa053c0e54e0667193f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="f55e3-102">Procedura: convalidare file di mapping esterni e DBML</span><span class="sxs-lookup"><span data-stu-id="f55e3-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="f55e3-103">I file di mapping esterno e i file con estensione dbml modificati devono essere convalidati in base alle rispettive definizioni dello schema.</span><span class="sxs-lookup"><span data-stu-id="f55e3-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="f55e3-104">In questo argomento vengono descritti i passaggi per l'implementazione del processo di convalida per gli utenti di [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f55e3-104">This topic provides [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="f55e3-105">Per convalidare un file con estensione dbml o un file XML</span><span class="sxs-lookup"><span data-stu-id="f55e3-105">To validate a .dbml or XML file</span></span>  
  
1.  <span data-ttu-id="f55e3-106">In Visual Studio **File** dal menu **aprire**, quindi fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="f55e3-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="f55e3-107">Nel **Apri** finestra di dialogo fare clic su di dbml o un file di mapping XML che si desidera convalidare.</span><span class="sxs-lookup"><span data-stu-id="f55e3-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="f55e3-108">Il file viene aperto nel **Editor XML**.</span><span class="sxs-lookup"><span data-stu-id="f55e3-108">The file opens in the **XML Editor**.</span></span>  
  
3.  <span data-ttu-id="f55e3-109">Fare clic sulla finestra e quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f55e3-109">Right-click the window, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f55e3-110">Nel **proprietà** finestra, fare clic sui puntini di sospensione per il **schemi** proprietà.</span><span class="sxs-lookup"><span data-stu-id="f55e3-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="f55e3-111">Il **schemi XML** verrà visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f55e3-111">The **XML Schemas** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="f55e3-112">Notare la definizione dello schema adatta allo scopo.</span><span class="sxs-lookup"><span data-stu-id="f55e3-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    -   <span data-ttu-id="f55e3-113">DbmlSchema.xsd è la definizione dello schema per la convalida di un file dbml.</span><span class="sxs-lookup"><span data-stu-id="f55e3-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="f55e3-114">Per ulteriori informazioni, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f55e3-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="f55e3-115">LinqToSqlMapping.xsd è la definizione dello schema per la convalida di un file di mapping XML esterno.</span><span class="sxs-lookup"><span data-stu-id="f55e3-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="f55e3-116">Per ulteriori informazioni, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="f55e3-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6.  <span data-ttu-id="f55e3-117">Nel **utilizzare** colonna della riga di definizione dello schema desiderato, fare clic per aprire la casella di riepilogo a discesa e quindi fare clic su **utilizzano questo schema**.</span><span class="sxs-lookup"><span data-stu-id="f55e3-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="f55e3-118">Il file di definizione dello schema è ora associato al file di mapping DBML o XML.</span><span class="sxs-lookup"><span data-stu-id="f55e3-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="f55e3-119">Assicurarsi che non siano selezionate altre definizioni dello schema.</span><span class="sxs-lookup"><span data-stu-id="f55e3-119">Make sure no other schema definitions are selected.</span></span>  
  
7.  <span data-ttu-id="f55e3-120">Nel **vista** menu, fare clic su **elenco errori**.</span><span class="sxs-lookup"><span data-stu-id="f55e3-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="f55e3-121">Determinare se sono stati generati errori, avvisi o messaggi.</span><span class="sxs-lookup"><span data-stu-id="f55e3-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="f55e3-122">In caso contrario, il file XML è valido per la definizione dello schema.</span><span class="sxs-lookup"><span data-stu-id="f55e3-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="f55e3-123">Metodo alternativo per fornire la definizione dello schema</span><span class="sxs-lookup"><span data-stu-id="f55e3-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="f55e3-124">Se per qualche motivo XSD appropriato file non viene visualizzato nel **schemi XML** nella finestra di dialogo è possibile scaricare il file XSD da un argomento della Guida.</span><span class="sxs-lookup"><span data-stu-id="f55e3-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="f55e3-125">I passaggi seguenti consentono di salvare il file scaricato nel formato Unicode richiesto dall'editor XML di [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f55e3-125">The following steps help you save the downloaded file in the Unicode format required by the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="f55e3-126">Per copiare un file di definizione dello schema da un argomento della Guida</span><span class="sxs-lookup"><span data-stu-id="f55e3-126">To copy a schema definition file from a Help topic</span></span>  
  
1.  <span data-ttu-id="f55e3-127">Individuare l'argomento della Guida che contiene la definizione dello schema descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f55e3-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    -   <span data-ttu-id="f55e3-128">Per i file con estensione dbml, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f55e3-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="f55e3-129">Per i file di mapping esterno, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="f55e3-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2.  <span data-ttu-id="f55e3-130">Fare clic su **Copia codice** per copiare il file di codice negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f55e3-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="f55e3-131">Avviare il Blocco note per creare un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="f55e3-131">Start Notepad to create a new file.</span></span>  
  
4.  <span data-ttu-id="f55e3-132">Incollare il codice dagli Appunti nel file del Blocco note.</span><span class="sxs-lookup"><span data-stu-id="f55e3-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5.  <span data-ttu-id="f55e3-133">Nel blocco note di **File** menu, fare clic su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="f55e3-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6.  <span data-ttu-id="f55e3-134">Nel **codifica** , quindi selezionare **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="f55e3-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f55e3-135">Questa selezione assicura che il file di testo sia preceduto dal marcatore dell'ordine di byte Unicode 16 (`FFFE`).</span><span class="sxs-lookup"><span data-stu-id="f55e3-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7.  <span data-ttu-id="f55e3-136">Nel **nome File** casella, creare un nome di file con estensione XSD.</span><span class="sxs-lookup"><span data-stu-id="f55e3-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f55e3-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f55e3-137">See Also</span></span>  
 [<span data-ttu-id="f55e3-138">Riferimento</span><span class="sxs-lookup"><span data-stu-id="f55e3-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
