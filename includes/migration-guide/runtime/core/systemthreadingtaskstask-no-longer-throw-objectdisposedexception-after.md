---
ms.openlocfilehash: 3eab96149be1e40d528cfd552bbe05ca766cf4e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620271"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>System.Threading.Tasks.Task non genera più ObjectDisposedException dopo l'eliminazione dell'oggetto

#### <a name="details"></a>Dettagli

Ad eccezione di <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, i metodi <xref:System.Threading.Tasks.Task?displayProperty=fullName> non generano più un'eccezione <xref:System.ObjectDisposedException?displayProperty=fullName> successivamente all'eliminazione dell'oggetto. Questa modifica supporta l'uso di attività memorizzate nella cache. Ad esempio, un metodo può restituire un'attività memorizzata nella cache per rappresentare un'operazione già completata anziché allocare una nuova attività. Ciò non è possibile nelle versioni precedenti di .NET Framework, perché qualsiasi utente dell'attività può rimuoverla e renderla così inutilizzabile.

#### <a name="suggestion"></a>Suggerimento

Tenere presente che i metodi Task potrebbero non generare più eccezioni <xref:System.ObjectDisposedException?displayProperty=fullName> nei casi in cui viene eliminato l'oggetto. Se un'app dipende da questa eccezione per venire a conoscenza dell'eliminazione di un'attività, è necessario aggiornarla in modo che controlli in modo esplicito lo stato dell'attività tramite <xref:System.Threading.Tasks.Task.Status>.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime|
