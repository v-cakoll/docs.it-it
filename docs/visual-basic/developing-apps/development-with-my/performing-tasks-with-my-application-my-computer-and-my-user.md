---
title: Esecuzione di attività mediante My.Application, My.Computer e My.User (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 84ac57bf1bcf60664e2b18fed16a3bbe6c03dc68
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2018
ms.locfileid: "42755008"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="369d9-102">Esecuzione di attività mediante My.Application, My.Computer e My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="369d9-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>
<span data-ttu-id="369d9-103">I tre principali `My` sono oggetti che forniscono funzionalità di accesso a informazioni e comunemente utilizzata `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), e `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="369d9-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="369d9-104">È possibile usare questi oggetti per accedere alle informazioni correlate per l'applicazione corrente, che l'applicazione è installata nel computer o l'utente corrente dell'applicazione, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="369d9-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="369d9-105">My. Application, My. computer e My. User</span><span class="sxs-lookup"><span data-stu-id="369d9-105">My.Application, My.Computer, and My.User</span></span>  
 <span data-ttu-id="369d9-106">Gli esempi seguenti illustrano come le informazioni possono essere recuperati tramite `My`.</span><span class="sxs-lookup"><span data-stu-id="369d9-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 <span data-ttu-id="369d9-107">Oltre il recupero di informazioni, i membri esposti attraverso i tre oggetti consentono anche di eseguire i metodi correlati a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="369d9-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="369d9-108">Ad esempio, è possibile accedere un'ampia gamma di metodi per modificare i file o aggiornare il Registro di sistema tramite `My.Computer`.</span><span class="sxs-lookup"><span data-stu-id="369d9-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="369d9-109">I/o file è notevolmente più semplice e rapido con `My`, che include un'ampia gamma di metodi e proprietà per la modifica dei file, directory e le unità.</span><span class="sxs-lookup"><span data-stu-id="369d9-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="369d9-110">Il <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> oggetto consente di leggere da file strutturati di grandi dimensioni che sono delimitati o campi a larghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="369d9-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="369d9-111">In questo esempio si apre la `TextFieldParser` `reader` e lo usa per leggere da `C:\TestFolder1\test1.txt`.</span><span class="sxs-lookup"><span data-stu-id="369d9-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 <span data-ttu-id="369d9-112">`My.Application` Consente di modificare le impostazioni cultura per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="369d9-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="369d9-113">Nell'esempio seguente viene illustrato come può chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="369d9-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="369d9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="369d9-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="369d9-115">Dipendenza di My dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="369d9-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
