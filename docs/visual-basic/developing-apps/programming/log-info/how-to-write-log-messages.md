---
title: 'Procedura: scrivere messaggi di log (Visual Basic)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ffc45b93250ba9e909776352b702be2e8295435d
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-log-messages-visual-basic"></a><span data-ttu-id="2cbf5-102">Procedura: scrivere messaggi di log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cbf5-102">How to: Write Log Messages (Visual Basic)</span></span>
<span data-ttu-id="2cbf5-103">È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare le informazioni sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-103">You can use the `My.Application.Log` and `My.Log` objects to log information about your application.</span></span> <span data-ttu-id="2cbf5-104">Questo esempio illustra come usare il metodo `My.Application.Log.WriteEntry` per registrare le informazioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information.</span></span>  
  
 <span data-ttu-id="2cbf5-105">Per registrare le informazioni sulle eccezioni, usare il metodo `My.Application.Log.WriteException`. Vedere [Procedura: Registrare eccezioni](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="2cbf5-105">For logging exception information, use the `My.Application.Log.WriteException` method; see [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cbf5-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2cbf5-106">Example</span></span>  
 <span data-ttu-id="2cbf5-107">Nell'esempio seguente viene usato il metodo `My.Application.Log.WriteEntry` per scrivere le informazioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-107">This example uses the `My.Application.Log.WriteEntry` method to write out the trace information.</span></span>  
  
 <span data-ttu-id="2cbf5-108">[!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2cbf5-108">[!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2cbf5-109">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2cbf5-109">.NET Framework Security</span></span>  
 <span data-ttu-id="2cbf5-110">Verificare che i dati scritti nel log non contengano informazioni riservate, ad esempio le password degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-110">Make sure the data you write to the log does not include sensitive information such as user passwords.</span></span> <span data-ttu-id="2cbf5-111">Per altre informazioni, vedere [Uso dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="2cbf5-111">For more information, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbf5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cbf5-112">See Also</span></span>  
 <span data-ttu-id="2cbf5-113"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2cbf5-113"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="2cbf5-114"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="2cbf5-114"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="2cbf5-115"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="2cbf5-115"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="2cbf5-116">[Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="2cbf5-116">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="2cbf5-117">[Procedura: Registrare eccezioni](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="2cbf5-117">[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span></span>  
 <span data-ttu-id="2cbf5-118">[Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="2cbf5-118">[Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="2cbf5-119">[Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="2cbf5-119">[Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span></span>  
 [<span data-ttu-id="2cbf5-120">Procedura dettagliata: Filtro dell'output di My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="2cbf5-120">Walkthrough: Filtering My.Application.Log Output</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)

