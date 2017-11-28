---
title: "Esecuzione di attività mediante My.Application, My.Computer e My.User (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d55e0b3a126f2216d005c7bddbcaefb7d8f0a580
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="c2220-102">Esecuzione di attività mediante My.Application, My.Computer e My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2220-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>
<span data-ttu-id="c2220-103">Tre centrale `My` sono oggetti che consentono di accedere alle informazioni e in genere funzionalità `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), e `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="c2220-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="c2220-104">È possibile utilizzare questi oggetti per accedere alle informazioni correlate per l'applicazione corrente, che l'applicazione è installata nel computer o l'utente corrente dell'applicazione, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="c2220-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="c2220-105">My. Application, My. computer e My. User</span><span class="sxs-lookup"><span data-stu-id="c2220-105">My.Application, My.Computer, and My.User</span></span>  
 <span data-ttu-id="c2220-106">Gli esempi seguenti illustrano come le informazioni possono essere recuperati tramite `My`.</span><span class="sxs-lookup"><span data-stu-id="c2220-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 <span data-ttu-id="c2220-107">Oltre il recupero delle informazioni, i membri esposti tramite questi tre oggetti consentono inoltre di eseguire i metodi correlati a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="c2220-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="c2220-108">Ad esempio, per accedere a diversi metodi per modificare i file o aggiornare il Registro di sistema tramite `My.Computer`.</span><span class="sxs-lookup"><span data-stu-id="c2220-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="c2220-109">I/o file è notevolmente più semplice e veloce con `My`, che include un'ampia gamma di metodi e proprietà per la modifica dei file, directory e unità.</span><span class="sxs-lookup"><span data-stu-id="c2220-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="c2220-110">Il <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> oggetto consente di leggere da file strutturati di grandi dimensioni che sono delimitati o campi a larghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="c2220-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="c2220-111">Questo esempio viene aperto il `TextFieldParser``reader` e viene utilizzato per leggere da `C:\TestFolder1\test1.txt`.</span><span class="sxs-lookup"><span data-stu-id="c2220-111">This example opens the `TextFieldParser``reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 <span data-ttu-id="c2220-112">`My.Application`Consente di modificare le impostazioni cultura per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c2220-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="c2220-113">Nell'esempio seguente viene illustrato come è possibile chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="c2220-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c2220-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2220-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="c2220-115">Dipendenza di My dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="c2220-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
