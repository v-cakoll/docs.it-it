---
title: Errori durante la compilazione di XML schema nel progetto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 17886ececbd418ae60d6321c7a6278a1e982b9af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611280"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="ff387-102">Errori durante la compilazione di XML schema nel progetto</span><span class="sxs-lookup"><span data-stu-id="ff387-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="ff387-103">Si sono verificati errori durante la compilazione di XML schema nel progetto.</span><span class="sxs-lookup"><span data-stu-id="ff387-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="ff387-104">Per questo motivo, IntelliSense XML non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ff387-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="ff387-105">Si verifica un errore in uno schema di XML Schema Definition (XSD) incluso nel progetto.</span><span class="sxs-lookup"><span data-stu-id="ff387-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="ff387-106">Questo errore si verifica quando si aggiunge un file di schema (XSD) di XSD che è in conflitto con lo schema XSD esistente impostato per il progetto.</span><span class="sxs-lookup"><span data-stu-id="ff387-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="ff387-107">**ID errore:** BC36810</span><span class="sxs-lookup"><span data-stu-id="ff387-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ff387-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ff387-108">To correct this error</span></span>  
  
-   <span data-ttu-id="ff387-109">Fare doppio clic su avviso nella **elenco errori** finestra.</span><span class="sxs-lookup"><span data-stu-id="ff387-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="ff387-110">Visual Basic verrà visualizzata la posizione nel file XSD che rappresenta l'origine dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="ff387-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="ff387-111">Correggere l'errore nello schema XSD.</span><span class="sxs-lookup"><span data-stu-id="ff387-111">Correct the error in the XSD schema.</span></span>  
  
-   <span data-ttu-id="ff387-112">Assicurarsi che tutti i necessari file di schema (XSD) XSD sono inclusi nel progetto.</span><span class="sxs-lookup"><span data-stu-id="ff387-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="ff387-113">Potrebbe essere necessario fare clic su **Mostra tutti i file** nel **Project** file menu per visualizzare il XSD **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="ff387-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="ff387-114">Fare doppio clic su un file XSD e quindi fare clic su **Includi nel progetto** per includere il file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="ff387-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
-   <span data-ttu-id="ff387-115">Se si usa il codice XML alla procedura guidata Schema, questo errore può verificarsi se in grado di dedurre schemi più di una volta dalla stessa origine.</span><span class="sxs-lookup"><span data-stu-id="ff387-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="ff387-116">In questo caso, è possibile rimuovere i file di schema XSD esistenti dal progetto, aggiungere un nuovo file XML al modello di elemento di Schema e quindi indicare il codice XML alla procedura guidata Schema con tutte le origini XML applicabile per il progetto.</span><span class="sxs-lookup"><span data-stu-id="ff387-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
-   <span data-ttu-id="ff387-117">Se nessun errore è identificato nello schema XSD, il compilatore XML non dispone di informazioni sufficienti per fornire un messaggio di errore dettagliato.</span><span class="sxs-lookup"><span data-stu-id="ff387-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="ff387-118">È possibile ottenere informazioni più dettagliate sugli errori, facendo in modo che gli spazi dei nomi XML per i file con estensione XSD incluso nel progetto corrispondano gli spazi dei nomi XML identificate per lo Schema XML, impostare in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ff387-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff387-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff387-119">See also</span></span>
- [<span data-ttu-id="ff387-120">Finestra Elenco errori</span><span class="sxs-lookup"><span data-stu-id="ff387-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)
- [<span data-ttu-id="ff387-121">XML</span><span class="sxs-lookup"><span data-stu-id="ff387-121">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
