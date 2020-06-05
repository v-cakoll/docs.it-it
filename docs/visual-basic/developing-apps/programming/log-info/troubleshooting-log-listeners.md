---
title: 'Risoluzione dei problemi: Listener di log'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: 8d2d8294d9e9bb42d72fe4f6c37bf846bd644907
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398318"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a>Risoluzione dei problemi: listener di log (Visual Basic)

È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sugli eventi che si verificano nell'applicazione.  
  
 Per determinare i listener di log a cui sono inviati questi messaggi, vedere [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](walkthrough-determining-where-my-application-log-writes-information.md).  
  
 L'oggetto `Log` può usare il filtro di log per limitare la quantità di informazioni registrate. Se i filtri non sono configurati correttamente, i log possono contenere informazioni errate. Per altre informazioni sui filtri, vedere [Procedura dettagliata: filtro dell'output di My.Application.Log](walkthrough-filtering-my-application-log-output.md).  
  
 Se tuttavia un log è configurato in modo errato, potrebbero essere necessarie maggiori informazioni sulla configurazione corrente. È possibile ottenere tali informazioni grazie alla proprietà avanzata `TraceSource` del log.  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a>Per determinare i listener di log per l'oggetto Log nel codice  
  
1. Importare lo spazio dei nomi <xref:System.Diagnostics> all'inizio del file di codice. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
     [!code-vb[VbVbalrMyApplicationLog#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#13)]  
  
2. Creare una funzione che consente di restituire una stringa costituita dalle informazioni relative a ognuno dei listener di log.  
  
     [!code-vb[VbVbalrMyApplicationLog#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#14)]  
  
3. Passare la raccolta dei listener di traccia del log alla funzione `GetListeners` e visualizzare il valore restituito.  
  
     [!code-vb[VbVbalrMyApplicationLog#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#19)]  
  
     Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Utilizzo dei log applicazione](working-with-application-logs.md)
- [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](walkthrough-determining-where-my-application-log-writes-information.md)
