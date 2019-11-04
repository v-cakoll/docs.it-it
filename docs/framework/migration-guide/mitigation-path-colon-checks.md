---
title: 'Mitigazione: Verifica della presenza dei due punti nel percorso'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: e88643fea3bd507289436f41880a2de34117884f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457905"
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

- [Compatibilità delle applicazioni](application-compatibility.md)
