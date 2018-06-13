---
title: 'Mitigazione: Verifica della presenza dei due punti nel percorso'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a54220a90a5120d13c89232d30ab40140c324097
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33387380"
---
# <a name="mitigation-path-colon-checks"></a>Mitigazione: Verifica della presenza dei due punti nel percorso
A partire dalle applicazioni dedicate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], sono state apportate alcune modifiche per supportare i percorsi in precedenza non supportati (entrambi in termini di lunghezza e il formato). In particolare, i controlli per la sintassi del separatore dell'unità appropriata (due punti) sono stati resi più corretti.  
  
## <a name="impact"></a>Impatto  
 Queste modifiche bloccano alcuni percorsi URI supportati in precedenza dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>.  
  
## <a name="mitigation"></a>Mitigazione  
 Per risolvere il problema di un percorso in precedenza accettabile che non è più supportato dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, è possibile eseguire queste operazioni:  
  
-   Rimuovere manualmente lo schema da un URL. Ad esempio, rimuovere `file://` da un URL.  
  
-   Passare l'URI a un costruttore <xref:System.Uri> e recuperare il valore della proprietà <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>.  
  
-   Rifiutare esplicitamente la normalizzazione del nuovo percorso impostando il commutatore `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> su `true`.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Modifiche di reindirizzamento](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
