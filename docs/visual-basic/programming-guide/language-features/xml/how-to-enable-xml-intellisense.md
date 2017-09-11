---
title: 'Procedura: abilitare IntelliSense XML in Visual Basic | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: e367016c93586ad34492628b6a4384a5ef1b6acd
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-enable-xml-intellisense-in-visual-basic"></a><span data-ttu-id="69c7e-102">Procedura: abilitare IntelliSense XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="69c7e-102">How to: Enable XML IntelliSense in Visual Basic</span></span>
<span data-ttu-id="69c7e-103">IntelliSense XML in Visual Basic consente il completamento di word per gli elementi definiti in uno schema XML.</span><span class="sxs-lookup"><span data-stu-id="69c7e-103">XML IntelliSense in Visual Basic provides word completion for elements that are defined in an XML schema.</span></span> <span data-ttu-id="69c7e-104">Per abilitare IntelliSense XML in Visual Basic, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="69c7e-104">To enable XML IntelliSense in Visual Basic, you must do the following:</span></span>  
  
1.  <span data-ttu-id="69c7e-105">Ottenere i file XML schema (XSD) per i file XML che l'applicazione dovrà leggere o scrivere.</span><span class="sxs-lookup"><span data-stu-id="69c7e-105">Obtain the XML schema (XSD) file or files for the XML files that your application will read from or write to.</span></span>  
  
2.  <span data-ttu-id="69c7e-106">Includere i file di schema XML nel progetto.</span><span class="sxs-lookup"><span data-stu-id="69c7e-106">Include the XML schema files in your project.</span></span>  
  
3.  <span data-ttu-id="69c7e-107">Importare la destinazione dello spazio dei nomi o spazi dei nomi in un progetto o del file di codice.</span><span class="sxs-lookup"><span data-stu-id="69c7e-107">Import the target namespace or namespaces into your code file or project.</span></span> <span data-ttu-id="69c7e-108">Uno spazio dei nomi di destinazione è identificato dal `targetNamespace` o `tns` dello schema XSD.</span><span class="sxs-lookup"><span data-stu-id="69c7e-108">A target namespace is identified by the `targetNamespace` or `tns` attribute of your XSD schema.</span></span>  
  
     <span data-ttu-id="69c7e-109">Per importare uno spazio dei nomi di destinazione, utilizzare il `Imports` istruzione oppure aggiungere uno spazio dei nomi per tutti i file di codice in un progetto usando il **riferimenti** pagina di progettazione.</span><span class="sxs-lookup"><span data-stu-id="69c7e-109">To import a target namespace, use the `Imports` statement, or add a namespace for all code files in a project by using the **References** page of the Project Designer.</span></span>  
  
 <span data-ttu-id="69c7e-110">Per ulteriori informazioni sulle funzionalità di IntelliSense XML in Visual Basic, vedere [IntelliSense XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="69c7e-110">For more information on the capabilities of XML IntelliSense in Visual Basic, see [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).</span></span> <span data-ttu-id="69c7e-111">Per ulteriori informazioni sull'importazione di spazi dei nomi XML, vedere [istruzione Imports (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) o [pagina riferimenti, Progettazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="69c7e-111">For more information on importing XML namespaces, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) or [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="69c7e-112">![collegamento a video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") per una versione video di questo argomento, vedere [procedura: abilitare IntelliSense XML in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466).</span><span class="sxs-lookup"><span data-stu-id="69c7e-112">![link to video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") For a video version of this topic, see [Video How to: Enable XML IntelliSense in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466).</span></span> <span data-ttu-id="69c7e-113">Per una dimostrazione video correlata, vedere [come posso abilitare IntelliSense XML e spazi dei nomi XML utilizzare?](http://go.microsoft.com/fwlink/?LinkId=143035).</span><span class="sxs-lookup"><span data-stu-id="69c7e-113">For a related video demonstration, see [How Do I Enable XML IntelliSense and Use XML Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035).</span></span>  
  
## <a name="enable-xml-intellisense-in-visual-basic"></a><span data-ttu-id="69c7e-114">Abilitare IntelliSense XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="69c7e-114">Enable XML IntelliSense in Visual Basic</span></span>  
 <span data-ttu-id="69c7e-115">Se si dispone di un file XML ma che non è un file di schema XSD, in SP1 è possibile creare un file di schema XSD utilizzando il XML Schema Wizard.</span><span class="sxs-lookup"><span data-stu-id="69c7e-115">If you have an XML file but you do not have an XSD schema file for it, in SP1 you can create an XSD schema file by using the XML to Schema Wizard.</span></span> <span data-ttu-id="69c7e-116">È inoltre possibile utilizzare l'inferenza dello schema nell'Editor XML di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="69c7e-116">You can also use schema inference in the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-the-xml-to-schema-wizard-requires-sp1"></a><span data-ttu-id="69c7e-117">Per creare un file di schema XSD per un file XML utilizzando il XML Schema Wizard (richiede SP1)</span><span class="sxs-lookup"><span data-stu-id="69c7e-117">To create an XSD schema file for an XML file by using the XML to Schema Wizard (requires SP1)</span></span>  
  
1.  <span data-ttu-id="69c7e-118">Nel progetto, fare clic su **Aggiungi nuovo elemento** sul **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="69c7e-118">In your project, click **Add New Item** on the **Project** menu.</span></span>  
  
2.  <span data-ttu-id="69c7e-119">Selezionare il **Xml in Schema** modello di elemento da una di **dati** o **elementi comuni** categorie dei modelli.</span><span class="sxs-lookup"><span data-stu-id="69c7e-119">Select the **Xml to Schema** item template from either the **Data** or **Common Items** template categories.</span></span>  
  
3.  <span data-ttu-id="69c7e-120">Specificare un nome di file per i file XSD che verranno archiviati in set di schemi derivati e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="69c7e-120">Provide a file name for the XSD file or files that the inferred schema set will be stored in, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="69c7e-121">Nel **del set di schemi XML dedurre da documenti XML** finestra, aggiungere uno o più documenti XML per dedurre lo schema XML da impostare.</span><span class="sxs-lookup"><span data-stu-id="69c7e-121">In the **Infer XML Schema set from XML documents** window, add one or more XML documents to infer the XML schema set from.</span></span>  
  
    -   <span data-ttu-id="69c7e-122">Per aggiungere i file di testo che contengono documenti XML mediante Esplora File, fare clic su **Aggiungi da File**.</span><span class="sxs-lookup"><span data-stu-id="69c7e-122">To add text files that contain XML documents by using File Explorer, click **Add from File**.</span></span>  
  
    -   <span data-ttu-id="69c7e-123">Per aggiungere un documento XML da un indirizzo HTTP, fare clic su **Aggiungi da Web**.</span><span class="sxs-lookup"><span data-stu-id="69c7e-123">To add an XML document from an HTTP address, click **Add from Web**.</span></span>  
  
    -   <span data-ttu-id="69c7e-124">Per copiare o digitare il contenuto di un documento XML nella procedura guidata, fare clic su **digitare o incollare XML**.</span><span class="sxs-lookup"><span data-stu-id="69c7e-124">To copy or type the contents of an XML document into the wizard, click **Type or paste XML**.</span></span>  
  
5.  <span data-ttu-id="69c7e-125">Quando specificate tutte le origini di documento XML da cui dedurre il set di schemi XML, fare clic su **OK** di inferire lo schema XML impostato.</span><span class="sxs-lookup"><span data-stu-id="69c7e-125">When you have specified all the XML document sources from which you want to infer the XML schema set, click **OK** to infer the XML schema set.</span></span> <span data-ttu-id="69c7e-126">Il set di schemi viene salvato nella cartella del progetto in uno o più file XSD.</span><span class="sxs-lookup"><span data-stu-id="69c7e-126">The schema set is saved in your project folder in one or more XSD files.</span></span> <span data-ttu-id="69c7e-127">(Per ogni spazio dei nomi XML nello schema, viene creato un file.)</span><span class="sxs-lookup"><span data-stu-id="69c7e-127">(For each XML namespace in the schema, a file is created.)</span></span>  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-schema-inference-in-the-visual-studio-xml-editor"></a><span data-ttu-id="69c7e-128">Per creare un file di schema XSD per un file XML con l'inferenza dello schema nell'Editor XML di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="69c7e-128">To create an XSD schema file for an XML file by using schema inference in the Visual Studio XML Editor</span></span>  
  
1.  <span data-ttu-id="69c7e-129">Modificare il file XML in Progettazione XML di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="69c7e-129">Edit the XML file in the Visual Studio XML Designer.</span></span>  
  
2.  <span data-ttu-id="69c7e-130">Quando il cursore è posizionato all'interno del file XML, il **XML** verrà visualizzato il menu.</span><span class="sxs-lookup"><span data-stu-id="69c7e-130">When the cursor is somewhere in the XML file, the **XML** menu appears.</span></span> <span data-ttu-id="69c7e-131">Fare clic su **Create Schema** sul **XML** menu.</span><span class="sxs-lookup"><span data-stu-id="69c7e-131">Click **Create Schema** on the **XML** menu.</span></span> <span data-ttu-id="69c7e-132">Viene creato un file XSD dallo schema XSD dedotto dal file XML.</span><span class="sxs-lookup"><span data-stu-id="69c7e-132">An XSD file is created from XSD schema inferred from the XML file.</span></span>  
  
3.  <span data-ttu-id="69c7e-133">Salvare il file di schema XSD.</span><span class="sxs-lookup"><span data-stu-id="69c7e-133">Save the XSD schema file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69c7e-134">Schemi XSD diversi potrebbero essere dedotto da più documenti XML che devono avere lo stesso schema.</span><span class="sxs-lookup"><span data-stu-id="69c7e-134">Different XSD schemas might be inferred from multiple XML documents that are intended to have the same schema.</span></span> <span data-ttu-id="69c7e-135">Ciò può verificarsi quando vengono trovati determinati elementi e attributi in un file XML e non in un'altra o quando sono inclusi elementi in ordine diverso, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="69c7e-135">This can occur when particular elements and attributes are found in one XML file and not in another, or when elements are included in different order, for example.</span></span> <span data-ttu-id="69c7e-136">Quando si utilizza l'inferenza dello schema XSD, è necessario rivedere gli schemi XSD derivati per completezza e accuratezza.</span><span class="sxs-lookup"><span data-stu-id="69c7e-136">You should review inferred XSD schemas for completeness and accuracy when you use XSD schema inference.</span></span>  
  
#### <a name="to-include-an-xsd-schema-file"></a><span data-ttu-id="69c7e-137">Per includere un file di schema XSD</span><span class="sxs-lookup"><span data-stu-id="69c7e-137">To include an XSD schema file</span></span>  
  
-   <span data-ttu-id="69c7e-138">Per impostazione predefinita, è possibile vedere i file XSD nei progetti Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="69c7e-138">By default, you cannot see XSD files in Visual Basic projects.</span></span> <span data-ttu-id="69c7e-139">Se il file XSD è già incluso nelle cartelle per il progetto, fare clic su di **Mostra tutti i file** pulsante **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="69c7e-139">If your XSD file is already included in the folders for your project, click the **Show All Files** button in **Solution Explorer**.</span></span> <span data-ttu-id="69c7e-140">Individuare il file XSD in **Esplora**, il file e fare clic su **includere File nel progetto**.</span><span class="sxs-lookup"><span data-stu-id="69c7e-140">Locate the XSD file in **Solution Explorer**, right-click the file, and click **Include File in Project**.</span></span>  
  
-   <span data-ttu-id="69c7e-141">Se il file XSD non è già parte del progetto, in **Esplora soluzioni**, fare clic sulla cartella in cui si desidera archiviare il file XSD, scegliere **Aggiungi**, quindi fare clic su **elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="69c7e-141">If your XSD file is not already part of your project, in **Solution Explorer**, right-click the folder in which you want to store the XSD file, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="69c7e-142">Individuare il file XSD e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="69c7e-142">Locate your XSD file and then click **Add**.</span></span>  
  
#### <a name="to-import-an-xml-namespace-in-a-code-file"></a><span data-ttu-id="69c7e-143">Per importare uno spazio dei nomi XML in un file di codice</span><span class="sxs-lookup"><span data-stu-id="69c7e-143">To import an XML namespace in a code file</span></span>  
  
1.  <span data-ttu-id="69c7e-144">Identificare lo spazio dei nomi di destinazione dallo schema XSD.</span><span class="sxs-lookup"><span data-stu-id="69c7e-144">Identify the target namespace from your XSD schema.</span></span>  
  
2.  <span data-ttu-id="69c7e-145">All'inizio del file di codice, aggiungere un `Imports` istruzione per lo spazio dei nomi XML destinazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="69c7e-145">At the beginning of the code file, add an `Imports` statement for the target XML namespace, as shown in the following example.</span></span>  
  
     <span data-ttu-id="69c7e-146">[!code-vb[VbXMLSamples n.&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="69c7e-146">[!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]</span></span>  
  
     <span data-ttu-id="69c7e-147">Per importare uno spazio dei nomi XML come spazio dei nomi predefinito, ovvero lo spazio dei nomi che viene applicato agli elementi XML e attributi che non hanno un prefisso dello spazio dei nomi, aggiungere un `Imports` istruzione per lo spazio dei nomi XML predefinito di destinazione.</span><span class="sxs-lookup"><span data-stu-id="69c7e-147">To import an XML namespace as the default namespace, that is, the namespace that is applied to XML elements and attributes that do not have a namespace prefix, add an `Imports` statement for the target default XML namespace.</span></span> <span data-ttu-id="69c7e-148">Non specificare un prefisso dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="69c7e-148">Do not specify a namespace prefix.</span></span> <span data-ttu-id="69c7e-149">Di seguito è riportato un esempio di un `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="69c7e-149">Following is an example of an `Imports` statement.</span></span>  
  
     <span data-ttu-id="69c7e-150">[!code-vb[&#50; VbXmlSamples](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="69c7e-150">[!code-vb[VbXmlSamples#50](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]</span></span>  
  
#### <a name="to-import-an-xml-namespace-for-all-files-in-a-project"></a><span data-ttu-id="69c7e-151">Per importare uno spazio dei nomi XML per tutti i file in un progetto</span><span class="sxs-lookup"><span data-stu-id="69c7e-151">To import an XML namespace for all files in a project</span></span>  
  
1.  <span data-ttu-id="69c7e-152">Uno spazio dei nomi XML importato in un file di codice si applica solo tale file di codice.</span><span class="sxs-lookup"><span data-stu-id="69c7e-152">An XML namespace imported in a code file applies to that code file only.</span></span> <span data-ttu-id="69c7e-153">Per importare uno spazio dei nomi XML che si applica a tutti i file di codice in un progetto, aprire la finestra Progettazione progetti facendo doppio clic su **progetto** in **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="69c7e-153">To import an XML namespace that applies to all code files in a project, open the Project Designer by double-clicking **My Project** in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="69c7e-154">Nel **riferimenti** nella scheda il **spazi dei nomi importati** digitare lo spazio dei nomi XML sotto forma di una dichiarazione dello spazio dei nomi XML completa (ad esempio, `<xmlns: ns="http://sampleNamespace">`).</span><span class="sxs-lookup"><span data-stu-id="69c7e-154">On the **References** tab, in the **Imported namespaces** box, type the target XML namespace in the form of a full XML namespace declaration (for example, `<xmlns: ns="http://sampleNamespace">`).</span></span> <span data-ttu-id="69c7e-155">Se lo spazio dei nomi XML non specifica un prefisso dello spazio dei nomi, lo spazio dei nomi sarà lo spazio dei nomi XML predefinito per il progetto.</span><span class="sxs-lookup"><span data-stu-id="69c7e-155">If the target XML namespace does not specify a namespace prefix, the namespace will be the default XML namespace for the project.</span></span>  
  
3.  <span data-ttu-id="69c7e-156">Fare clic su **Aggiungi importazione utente**.</span><span class="sxs-lookup"><span data-stu-id="69c7e-156">Click **Add User Import**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c7e-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69c7e-157">See Also</span></span>  
 <span data-ttu-id="69c7e-158">[Istruzione Imports (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="69c7e-158">[Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="69c7e-159"> [Riferimenti (pagina), Creazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="69c7e-159"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="69c7e-160"> [IntelliSense XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)</span><span class="sxs-lookup"><span data-stu-id="69c7e-160"> [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)</span></span>

