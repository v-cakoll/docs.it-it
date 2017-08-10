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
# <a name="mitigation-culture-and-asynchronous-operations"></a>Mitigazione: Impostazioni cultura e operazioni asincrone
Per app destinate a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] e versioni successive, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> vengono archiviate nell'oggetto <xref:System.Threading.ExecutionContext> del thread, che passa attraverso operazioni asincrone.  
  
## <a name="impact"></a>Impatto  
 In seguito a questa modifica, le modifiche a <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> si riflettono sulle attività eseguite successivamente in modo asincrono. Questo comportamento è diverso rispetto alle versioni precedenti di .NET Framework, in cui gli oggetti <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> vengono reimpostati sui valori predefiniti del sistema in tutte le attività asincrone.  
  
## <a name="mitigation"></a>Attenuazione  
 Le app interessate da questa modifica possono aggirare il problema in uno dei due modi:  
  
-   Impostando in modo esplicito la proprietà <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> come prima operazione in un'attività asincrona.  
  
-   Scegliendo come in precedenza di non propagare <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> aggiungendo il seguente elemento `AppContextSwitchOverrides` al file di configurazione dell'applicazione:  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   Scegliendo come in precedenza di non propagare <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> impostando la seguente opzione di compatibilità a livello di codice:  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Modifiche di reindirizzamento](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

