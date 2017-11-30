---
title: Errori durante la compilazione di XML schema nel progetto
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords: BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07233ed1c68f85878ffdd7131f64e30e158dc350
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="313cd-102">Errori durante la compilazione di XML schema nel progetto</span><span class="sxs-lookup"><span data-stu-id="313cd-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="313cd-103">Si sono verificati errori durante la compilazione di XML schema nel progetto.</span><span class="sxs-lookup"><span data-stu-id="313cd-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="313cd-104">Per questo motivo, IntelliSense XML non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="313cd-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="313cd-105">Si verifica un errore in uno schema di XML Schema Definition (XSD) incluso nel progetto.</span><span class="sxs-lookup"><span data-stu-id="313cd-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="313cd-106">Questo errore si verifica quando si aggiunge un file di schema (XSD) XSD che è in conflitto con lo schema XSD esistente impostato per il progetto.</span><span class="sxs-lookup"><span data-stu-id="313cd-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="313cd-107">**ID errore:** BC36810</span><span class="sxs-lookup"><span data-stu-id="313cd-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="313cd-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="313cd-108">To correct this error</span></span>  
  
-   <span data-ttu-id="313cd-109">Fare doppio clic su avviso nel **elenco degli errori** finestra.</span><span class="sxs-lookup"><span data-stu-id="313cd-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="313cd-110">Visual Basic verrà visualizzata la posizione nel file XSD che rappresenta l'origine dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="313cd-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="313cd-111">Per correggere l'errore nello schema XSD.</span><span class="sxs-lookup"><span data-stu-id="313cd-111">Correct the error in the XSD schema.</span></span>  
  
-   <span data-ttu-id="313cd-112">Verificare che tutti i necessari file di schema (XSD) XSD sono inclusi nel progetto.</span><span class="sxs-lookup"><span data-stu-id="313cd-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="313cd-113">Potrebbe essere necessario fare clic su **Mostra tutti i file** sul **progetto** menu per visualizzare il XSD file **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="313cd-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="313cd-114">Fare doppio clic su un file XSD e quindi fare clic su **Includi nel progetto** per includere il file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="313cd-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
-   <span data-ttu-id="313cd-115">Se si utilizza il codice XML per la procedura guidata Schema, questo errore può verificarsi se si dedurre schemi più volte la stessa origine.</span><span class="sxs-lookup"><span data-stu-id="313cd-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="313cd-116">In questo caso, è possibile rimuovere i file di schema XSD esistenti dal progetto, aggiungere un nuovo codice XML per il modello di elemento di Schema e quindi indicare il codice XML per la procedura guidata Schema con tutte le origini XML applicabili per il progetto.</span><span class="sxs-lookup"><span data-stu-id="313cd-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
-   <span data-ttu-id="313cd-117">Se nello schema XSD non viene identificato alcun errore, il compilatore XML non dispone di informazioni sufficienti per fornire un messaggio di errore dettagliato.</span><span class="sxs-lookup"><span data-stu-id="313cd-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="313cd-118">È possibile ottenere informazioni dettagliate sull'errore, facendo in modo che gli spazi dei nomi XML per i file XSD incluso nel progetto corrispondano gli spazi dei nomi XML identificati per lo Schema XML, impostare in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="313cd-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313cd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="313cd-119">See Also</span></span>  
 [<span data-ttu-id="313cd-120">Finestra Elenco errori</span><span class="sxs-lookup"><span data-stu-id="313cd-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)  
 [<span data-ttu-id="313cd-121">XML</span><span class="sxs-lookup"><span data-stu-id="313cd-121">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
