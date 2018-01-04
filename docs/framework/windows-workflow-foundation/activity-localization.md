---
title: "Localizzazione di attività"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccabcda9e26751db80ee7e955458d0eee0cae7e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="activity-localization"></a><span data-ttu-id="55159-102">Localizzazione di attività</span><span class="sxs-lookup"><span data-stu-id="55159-102">Activity Localization</span></span>
<span data-ttu-id="55159-103">Quando le applicazioni e i componenti del flusso di lavoro possono essere localizzati in altre impostazioni cultura e lingue, le stringhe di risorsa devono essere usate in modo da poter essere localizzate senza ricompilare.</span><span class="sxs-lookup"><span data-stu-id="55159-103">When workflow applications and components have the potential to be localized into other cultures and languages, resource strings should be used so that they can be localized without recompiling.</span></span>  
  
## <a name="activity-localization"></a><span data-ttu-id="55159-104">Localizzazione di attività</span><span class="sxs-lookup"><span data-stu-id="55159-104">Activity Localization</span></span>  
 <span data-ttu-id="55159-105">Come avviene con tutte le applicazioni che devono essere localizzate (rilasciate in versioni diverse per lingue e impostazioni cultura differenti), qualsiasi stringa visualizzata all'utente non deve essere inserita direttamente nel codice, bensì archiviata in un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="55159-105">As with all applications that must be localized (released in different versions for different languages and cultures), any strings that are displayed to the user should not be put directly in code, but rather stored in a resource file.</span></span> <span data-ttu-id="55159-106">Le stringhe sono quindi possibile accedere tramite <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`.</span><span class="sxs-lookup"><span data-stu-id="55159-106">The strings can then be accessed through <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`.</span></span> <span data-ttu-id="55159-107">Se si sta sviluppando un componente che viene distribuito in diverse lingue, si desidera anche usare stringhe di risorsa per i messaggi di convalida delle attività, i dati di rilevamento definiti dall'utente, i messaggi di traccia e quelli di errore.</span><span class="sxs-lookup"><span data-stu-id="55159-107">If you are developing a component that is distributed in several languages, you also want to use resource strings for activity validation messages, user-defined tracking data, tracing messages, and error messages as well.</span></span>  
  
 <span data-ttu-id="55159-108">Nell'esercizio seguente viene illustrato come usare un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="55159-108">The following exercise demonstrates how to use a resource file.</span></span>  
  
#### <a name="using-resource-files-for-localized-strings"></a><span data-ttu-id="55159-109">Uso di file di risorse per le stringhe localizzate</span><span class="sxs-lookup"><span data-stu-id="55159-109">Using resource files for localized strings</span></span>  
  
1.  <span data-ttu-id="55159-110">In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], pulsante destro del mouse sul progetto in **Esplora** e selezionare **Aggiungi...** , **Nuovo elemento...** .</span><span class="sxs-lookup"><span data-stu-id="55159-110">In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], right-click your project in **Solution Explorer** and select **Add…**, **New Item…**.</span></span>  
  
2.  <span data-ttu-id="55159-111">Selezionare **File di risorse** e denominare il file Errorresources.</span><span class="sxs-lookup"><span data-stu-id="55159-111">Select **Resources File** and name the file ErrorResources.resx.</span></span> <span data-ttu-id="55159-112">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="55159-112">Click **Add**.</span></span>  
  
3.  <span data-ttu-id="55159-113">Aprire il file di risorse.</span><span class="sxs-lookup"><span data-stu-id="55159-113">Open the resource file.</span></span> <span data-ttu-id="55159-114">Aggiungere una nuova voce con un **nome** ErrorString e **valore** "dell'attività non è valido."</span><span class="sxs-lookup"><span data-stu-id="55159-114">Add a new entry with a **Name** of ErrorString and a **Value** of "The activity is not valid."</span></span>  
  
4.  <span data-ttu-id="55159-115">Aggiungere le seguenti istruzioni `using` alla classe.</span><span class="sxs-lookup"><span data-stu-id="55159-115">Add the following `using` statements to your class.</span></span>  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
    ```  
  
5.  <span data-ttu-id="55159-116">Creare un gestore di risorse nel progetto.</span><span class="sxs-lookup"><span data-stu-id="55159-116">Create a resource manager in your project.</span></span>  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
    ```  
  
6.  <span data-ttu-id="55159-117">Ottenere la stringa dal gestore di risorse in cui è richiesta.</span><span class="sxs-lookup"><span data-stu-id="55159-117">Get the string from the resource manager where it is required.</span></span>  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
    ```  
  
 <span data-ttu-id="55159-118">Nell'esempio di codice seguente viene illustrato come usare le stringhe localizzate nel metodo <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="55159-118">The following code sample demonstrates how to utilize localized strings in the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span>  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```
