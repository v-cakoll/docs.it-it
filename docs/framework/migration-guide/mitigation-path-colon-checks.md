---
title: 'Mitigazione: Verifica della presenza dei due punti nel percorso'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: ee71f6ef1e70509e772aee2cc75d00c33122a92e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126225"
---
# <a name="mitigation-path-colon-checks"></a>Mitigazione: Verifica della presenza dei due punti nel percorso
A partire dalle applicazioni destinate a .NET Framework 4.6.2, sono state apportate alcune modifiche per supportare i percorsi in precedenza non supportati, sia in termini di lunghezza che di formato. In particolare, i controlli per la sintassi del separatore dell'unità appropriata (due punti) sono stati resi più corretti.  
  
## <a name="impact"></a>Impatto  
 Queste modifiche bloccano alcuni percorsi URI supportati in precedenza dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>.  
  
## <a name="mitigation"></a>Attenuazione  
 Per risolvere il problema di un percorso in precedenza accettabile che non è più supportato dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, è possibile eseguire queste operazioni:  
  
- Rimuovere manualmente lo schema da un URL. Ad esempio, rimuovere `file://` da un URL.  
  
- Passare l'URI a un costruttore <xref:System.Uri> e recuperare il valore della proprietà <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>.  
  
- Rifiutare esplicitamente la normalizzazione del nuovo percorso impostando il commutatore `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> su `true`.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Modifiche di reindirizzamento](retargeting-changes-in-the-net-framework-4-6-2.md)
