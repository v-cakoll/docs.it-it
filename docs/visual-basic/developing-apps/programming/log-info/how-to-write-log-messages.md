---
title: 'Procedura: Scrivere messaggi di log (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 4b4210983aa5bd57f1b0a89f2f06f089e98670f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594951"
---
# <a name="how-to-write-log-messages-visual-basic"></a><span data-ttu-id="4ad44-102">Procedura: Scrivere messaggi di log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ad44-102">How to: Write Log Messages (Visual Basic)</span></span>
<span data-ttu-id="4ad44-103">È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare le informazioni sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ad44-103">You can use the `My.Application.Log` and `My.Log` objects to log information about your application.</span></span> <span data-ttu-id="4ad44-104">Questo esempio illustra come usare il metodo `My.Application.Log.WriteEntry` per registrare le informazioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="4ad44-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information.</span></span>  
  
 <span data-ttu-id="4ad44-105">Per registrare le informazioni sulle eccezioni, usare il metodo `My.Application.Log.WriteException`. Vedere [Procedura: Registrare eccezioni](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="4ad44-105">For logging exception information, use the `My.Application.Log.WriteException` method; see [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ad44-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ad44-106">Example</span></span>  
 <span data-ttu-id="4ad44-107">Nell'esempio seguente viene usato il metodo `My.Application.Log.WriteEntry` per scrivere le informazioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="4ad44-107">This example uses the `My.Application.Log.WriteEntry` method to write out the trace information.</span></span>  
  
 [!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="4ad44-108">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4ad44-108">.NET Framework Security</span></span>  
 <span data-ttu-id="4ad44-109">Verificare che i dati scritti nel log non contengano informazioni riservate, ad esempio le password degli utenti.</span><span class="sxs-lookup"><span data-stu-id="4ad44-109">Make sure the data you write to the log does not include sensitive information such as user passwords.</span></span> <span data-ttu-id="4ad44-110">Per altre informazioni, vedere [Uso dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="4ad44-110">For more information, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad44-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ad44-111">See also</span></span>
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="4ad44-112">Utilizzo dei log applicazione</span><span class="sxs-lookup"><span data-stu-id="4ad44-112">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="4ad44-113">Procedura: Registrare eccezioni</span><span class="sxs-lookup"><span data-stu-id="4ad44-113">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="4ad44-114">Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="4ad44-114">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="4ad44-115">Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="4ad44-115">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="4ad44-116">Procedura dettagliata: Filtro dell'output di My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="4ad44-116">Walkthrough: Filtering My.Application.Log Output</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)
