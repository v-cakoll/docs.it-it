---
title: 'Mitigazione: Rendering di finestre WPF'
ms.date: 03/30/2017
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d54751ae0492e25f824eee6362e0f3bca446d75e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147628"
---
# <a name="mitigation-wpf-window-rendering"></a>Mitigazione: Rendering di finestre WPF
In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] in esecuzione in Windows 8 e versioni successive viene eseguito il rendering dell'intera finestra senza ritaglio quando la finestra si estende al di fuori di un singolo schermo in uno scenario di utilizzo di più monitor.  
  
## <a name="impact"></a>Impatto  
 In generale, il rendering di un'intera finestra su più monitor senza ritaglio è il comportamento previsto. Tuttavia, in Windows 7 e versioni precedenti le finestre WPF vengono ritagliate quando si estendono oltre un singolo schermo perché il rendering di una parte della finestra sul secondo monitor ha un impatto significativo sulle prestazioni.  
  
 L'impatto esatto del rendering di finestre WPF su più monitor in Windows 8 e versioni successive non è precisamente quantificabile poiché dipende da numerosi fattori. In alcuni casi, potrebbe produrre un impatto indesiderato sulle prestazioni, in particolare per gli utenti che eseguono applicazioni a elevato utilizzo di grafica e hanno finestre che si estendono su più monitor. In altri casi, si potrebbe semplicemente volere un comportamento coerente tra le versioni di .NET Framework.  
  
## <a name="mitigation"></a>Mitigazione  
 È possibile disabilitare questa modifica e ripristinare il comportamento precedente di ritaglio di una finestra WPF quando si estende oltre un singolo schermo. Questo risultato può essere raggiunto in due modi:  
  
-   Aggiungendo l'elemento `<EnableMultiMonitorDisplayClipping>` nella sezione `<appSettings>` del file di configurazione dell'applicazione, è possibile disabilitare o abilitare questo comportamento nelle app che eseguono Windows 8 o versione successiva. Ad esempio, la sezione di configurazione seguente disabilita il rendering senza ritaglio:  
  
    ```xml  
    <appSettings>  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
      </appSettings>  
    ```  
  
     L'impostazione di configurazione `<EnableMultiMonitorDisplayClipping>` può avere uno dei due valori seguenti:  
  
    -   `true`per consentire il ritaglio delle finestre in base ai confini del monitor durante il rendering.  
  
    -   `false`per disabilitare il ritaglio delle finestre in base ai confini del monitor durante il rendering.  
  
-   Impostando la proprietà <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> su `true` all'avvio dell'app.  
  
## <a name="see-also"></a>Vedere anche

- [Modifiche in fase di esecuzione](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
