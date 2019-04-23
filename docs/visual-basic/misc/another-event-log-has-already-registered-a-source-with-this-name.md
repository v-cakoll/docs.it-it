---
title: Un altro log eventi ha già registrato un'origine con questo nome
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: d932869504b2d8a5f3a948b190e5528bfcfa664f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314672"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a>Un altro log eventi ha già registrato un'origine con questo nome
Si è provato a scrivere una voce in un log eventi ma l'origine specificata è stata registrata in un altro log eventi.  
  
 Per consentire al componente <xref:System.Diagnostics.EventLog.Source%2A> di scrivere voci in un log, è necessario impostare la proprietà <xref:System.Diagnostics.EventLog> sull'istanza del componente. Quando si esegue questa operazione, viene controllato che l'origine specificata sia registrata nel log eventi in cui viene scritto il componente e, se necessario, viene chiamata la proprietà <xref:System.Diagnostics.EventLog.CreateEventSource%2A> .  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Rimuovere l'associazione tra l'origine e il primo log usando il metodo <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> o <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .  
  
2. Registrare l'origine nel nuovo log.  
  
## <a name="see-also"></a>Vedere anche

- [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
