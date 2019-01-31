---
title: 'Risoluzione dei problemi: listener di log (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: 3d21024a7ebda749f337a95b0fca419b529d2872
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662816"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="018cf-102">Risoluzione dei problemi: listener di log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="018cf-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="018cf-103">È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sugli eventi che si verificano nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="018cf-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="018cf-104">Per determinare i listener di log che ricevono questi messaggi, vedere [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="018cf-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="018cf-105">L'oggetto `Log` può usare il filtro di log per limitare la quantità di informazioni registrate.</span><span class="sxs-lookup"><span data-stu-id="018cf-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="018cf-106">Se i filtri non sono configurati correttamente, i log possono contenere informazioni errate.</span><span class="sxs-lookup"><span data-stu-id="018cf-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="018cf-107">Per altre informazioni sui filtri, vedere [Procedura dettagliata: Filtro dell'output di My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="018cf-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="018cf-108">Se tuttavia un log è configurato in modo errato, potrebbero essere necessarie maggiori informazioni sulla configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="018cf-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="018cf-109">È possibile ottenere tali informazioni grazie alla proprietà avanzata `TraceSource` del log.</span><span class="sxs-lookup"><span data-stu-id="018cf-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="018cf-110">Per determinare i listener di log per l'oggetto Log nel codice</span><span class="sxs-lookup"><span data-stu-id="018cf-110">To determine the log listeners for the Log object in code</span></span>  
  
1.  <span data-ttu-id="018cf-111">Importare lo spazio dei nomi <xref:System.Diagnostics> all'inizio del file di codice.</span><span class="sxs-lookup"><span data-stu-id="018cf-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="018cf-112">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="018cf-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]  
  
2.  <span data-ttu-id="018cf-113">Creare una funzione che consente di restituire una stringa costituita dalle informazioni relative a ognuno dei listener di log.</span><span class="sxs-lookup"><span data-stu-id="018cf-113">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]  
  
3.  <span data-ttu-id="018cf-114">Passare la raccolta dei listener di traccia del log alla funzione `GetListeners` e visualizzare il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="018cf-114">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]  
  
     <span data-ttu-id="018cf-115">Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="018cf-115">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018cf-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="018cf-116">See also</span></span>
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="018cf-117">Utilizzo dei log applicazione</span><span class="sxs-lookup"><span data-stu-id="018cf-117">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="018cf-118">Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="018cf-118">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
