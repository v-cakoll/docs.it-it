---
title: Errori durante la compilazione di XML schema nel progetto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 919c6873ba63addb776d756a58c44a3fe3f0ec3d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409628"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="df409-102">Errori durante la compilazione di XML schema nel progetto</span><span class="sxs-lookup"><span data-stu-id="df409-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="df409-103">Si sono verificati errori durante la compilazione degli XML Schema nel progetto.</span><span class="sxs-lookup"><span data-stu-id="df409-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="df409-104">Per questo motivo, IntelliSense XML non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="df409-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="df409-105">Si è verificato un errore in uno schema XSD (XML Schema Definition) incluso nel progetto.</span><span class="sxs-lookup"><span data-stu-id="df409-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="df409-106">Questo errore si verifica quando si aggiunge un file di schema XSD (XSD) in conflitto con il set di schemi XSD esistente per il progetto.</span><span class="sxs-lookup"><span data-stu-id="df409-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="df409-107">**ID errore:** BC36810</span><span class="sxs-lookup"><span data-stu-id="df409-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="df409-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="df409-108">To correct this error</span></span>  
  
- <span data-ttu-id="df409-109">Fare doppio clic sull'avviso nella finestra **Elenco errori** .</span><span class="sxs-lookup"><span data-stu-id="df409-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="df409-110">Visual Basic consentirà di passare al percorso nel file XSD che rappresenta l'origine dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="df409-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="df409-111">Correggere l'errore nello schema XSD.</span><span class="sxs-lookup"><span data-stu-id="df409-111">Correct the error in the XSD schema.</span></span>  
  
- <span data-ttu-id="df409-112">Verificare che tutti i file di schema XSD (. xsd) necessari siano inclusi nel progetto.</span><span class="sxs-lookup"><span data-stu-id="df409-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="df409-113">Potrebbe essere necessario fare clic su **Mostra tutti i file** nel menu **progetto** per visualizzare i file con estensione XSD in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="df409-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="df409-114">Fare clic con il pulsante destro del mouse su un file con estensione XSD, quindi scegliere **Includi nel progetto** per includere il file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="df409-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
- <span data-ttu-id="df409-115">Se si utilizza la procedura guidata XML per schema, questo errore può verificarsi se si deduce più di una volta gli schemi dalla stessa origine.</span><span class="sxs-lookup"><span data-stu-id="df409-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="df409-116">In questo caso, è possibile rimuovere i file di schema XSD esistenti dal progetto, aggiungere un nuovo modello di elemento XML a schema, quindi fornire la procedura guidata XML to schema con tutte le origini XML applicabili per il progetto.</span><span class="sxs-lookup"><span data-stu-id="df409-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
- <span data-ttu-id="df409-117">Se nello schema XSD non viene identificato alcun errore, è possibile che il compilatore XML non disponga di informazioni sufficienti per fornire un messaggio di errore dettagliato.</span><span class="sxs-lookup"><span data-stu-id="df409-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="df409-118">Se si verifica che gli spazi dei nomi XML per i file XSD inclusi nel progetto corrispondano agli spazi dei nomi XML identificati per il set di XML Schema in Visual Studio, è possibile ottenere informazioni più dettagliate sugli errori.</span><span class="sxs-lookup"><span data-stu-id="df409-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df409-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df409-119">See also</span></span>

- [<span data-ttu-id="df409-120">Finestra Elenco errori</span><span class="sxs-lookup"><span data-stu-id="df409-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)
- [<span data-ttu-id="df409-121">XML</span><span class="sxs-lookup"><span data-stu-id="df409-121">XML</span></span>](../../programming-guide/language-features/xml/index.md)
