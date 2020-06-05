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
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="ce43c-102">Risoluzione dei problemi: listener di log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce43c-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>

<span data-ttu-id="ce43c-103">È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sugli eventi che si verificano nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce43c-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="ce43c-104">Per determinare i listener di log a cui sono inviati questi messaggi, vedere [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="ce43c-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="ce43c-105">L'oggetto `Log` può usare il filtro di log per limitare la quantità di informazioni registrate.</span><span class="sxs-lookup"><span data-stu-id="ce43c-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="ce43c-106">Se i filtri non sono configurati correttamente, i log possono contenere informazioni errate.</span><span class="sxs-lookup"><span data-stu-id="ce43c-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="ce43c-107">Per altre informazioni sui filtri, vedere [Procedura dettagliata: filtro dell'output di My.Application.Log](walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="ce43c-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="ce43c-108">Se tuttavia un log è configurato in modo errato, potrebbero essere necessarie maggiori informazioni sulla configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="ce43c-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="ce43c-109">È possibile ottenere tali informazioni grazie alla proprietà avanzata `TraceSource` del log.</span><span class="sxs-lookup"><span data-stu-id="ce43c-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="ce43c-110">Per determinare i listener di log per l'oggetto Log nel codice</span><span class="sxs-lookup"><span data-stu-id="ce43c-110">To determine the log listeners for the Log object in code</span></span>  
  
1. <span data-ttu-id="ce43c-111">Importare lo spazio dei nomi <xref:System.Diagnostics> all'inizio del file di codice.</span><span class="sxs-lookup"><span data-stu-id="ce43c-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="ce43c-112">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="ce43c-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#13)]  
  
2. <span data-ttu-id="ce43c-113">Creare una funzione che consente di restituire una stringa costituita dalle informazioni relative a ognuno dei listener di log.</span><span class="sxs-lookup"><span data-stu-id="ce43c-113">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#14)]  
  
3. <span data-ttu-id="ce43c-114">Passare la raccolta dei listener di traccia del log alla funzione `GetListeners` e visualizzare il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="ce43c-114">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#19)]  
  
     <span data-ttu-id="ce43c-115">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce43c-115">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce43c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce43c-116">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="ce43c-117">Utilizzo dei log applicazione</span><span class="sxs-lookup"><span data-stu-id="ce43c-117">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="ce43c-118">Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="ce43c-118">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
