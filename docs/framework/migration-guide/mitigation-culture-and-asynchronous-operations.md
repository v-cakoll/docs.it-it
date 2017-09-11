---
title: 'Mitigazione: Impostazioni cultura e operazioni asincrone'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2cdb578-9923-47df-9ffd-5865333ac1a4
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: debcae8281c832d2815e1b9896fbbcb725c8ffc3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-asynchronous-operations"></a><span data-ttu-id="ee843-102">Mitigazione: Impostazioni cultura e operazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="ee843-102">Mitigation: Culture and Asynchronous Operations</span></span>
<span data-ttu-id="ee843-103">Per app destinate a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] e versioni successive, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> vengono archiviate nell'oggetto <xref:System.Threading.ExecutionContext> del thread, che passa attraverso operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="ee843-103">For apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and later versions, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are stored in a thread's <xref:System.Threading.ExecutionContext>, which flows across asynchronous operations.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="ee843-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="ee843-104">Impact</span></span>  
 <span data-ttu-id="ee843-105">In seguito a questa modifica, le modifiche a <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> si riflettono sulle attività eseguite successivamente in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="ee843-105">As a result of this change, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are reflected in tasks which are later run asynchronously.</span></span> <span data-ttu-id="ee843-106">Questo comportamento è diverso rispetto alle versioni precedenti di .NET Framework, in cui gli oggetti <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> vengono reimpostati sui valori predefiniti del sistema in tutte le attività asincrone.</span><span class="sxs-lookup"><span data-stu-id="ee843-106">This differs from the behavior of previous .NET Framework versions, which would reset <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to the system default  in all asynchronous tasks.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="ee843-107">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="ee843-107">Mitigation</span></span>  
 <span data-ttu-id="ee843-108">Le app interessate da questa modifica possono aggirare il problema in uno dei due modi:</span><span class="sxs-lookup"><span data-stu-id="ee843-108">Apps affected by this change can work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="ee843-109">Impostando in modo esplicito la proprietà <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> come prima operazione in un'attività asincrona.</span><span class="sxs-lookup"><span data-stu-id="ee843-109">By explicitly setting the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> property as the first operation in an asynchronous task.</span></span>  
  
-   <span data-ttu-id="ee843-110">Scegliendo come in precedenza di non propagare <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> aggiungendo il seguente elemento `AppContextSwitchOverrides` al file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="ee843-110">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by adding the following `AppContextSwitchOverrides` element to the application's configuration file:</span></span>  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="ee843-111">Scegliendo come in precedenza di non propagare <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> impostando la seguente opzione di compatibilità a livello di codice:</span><span class="sxs-lookup"><span data-stu-id="ee843-111">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by setting the following compatibility switch programatically:</span></span>  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ee843-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee843-112">See Also</span></span>  
 [<span data-ttu-id="ee843-113">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="ee843-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

