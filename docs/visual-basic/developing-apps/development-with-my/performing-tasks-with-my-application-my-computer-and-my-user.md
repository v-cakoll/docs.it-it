---
title: Esecuzione di attività mediante My.Application, My.Computer e My.User
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 55961d6857b690fc2726f541df8a5497a3207928
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411694"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="3c6af-102">Esecuzione di attività mediante My.Application, My.Computer e My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c6af-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>

<span data-ttu-id="3c6af-103">I tre `My` oggetti centrali che consentono di accedere alle informazioni e alle funzionalità comunemente utilizzate sono `My.Application` ( <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> ), `My.Computer` ( <xref:Microsoft.VisualBasic.Devices.Computer> ) e `My.User` () <xref:Microsoft.VisualBasic.ApplicationServices.User> .</span><span class="sxs-lookup"><span data-stu-id="3c6af-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="3c6af-104">Questi oggetti possono essere usati per accedere alle informazioni relative all'applicazione corrente, al computer in cui è installata l'applicazione o all'utente corrente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3c6af-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="3c6af-105">My. Application, My. computer e My. User</span><span class="sxs-lookup"><span data-stu-id="3c6af-105">My.Application, My.Computer, and My.User</span></span>  

 <span data-ttu-id="3c6af-106">Gli esempi seguenti illustrano come è possibile recuperare le informazioni usando `My` .</span><span class="sxs-lookup"><span data-stu-id="3c6af-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 <span data-ttu-id="3c6af-107">Oltre a recuperare le informazioni, i membri esposti tramite questi tre oggetti consentono inoltre di eseguire metodi correlati a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c6af-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="3c6af-108">Ad esempio, è possibile accedere a diversi metodi per modificare i file o aggiornare il registro di sistema tramite `My.Computer` .</span><span class="sxs-lookup"><span data-stu-id="3c6af-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="3c6af-109">L'I/O dei file è significativamente più semplice e veloce con `My` , che include un'ampia gamma di metodi e proprietà per la modifica di file, directory e unità.</span><span class="sxs-lookup"><span data-stu-id="3c6af-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="3c6af-110">L' <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> oggetto consente di leggere da file strutturati di grandi dimensioni con campi delimitati o a larghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="3c6af-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="3c6af-111">In questo esempio viene aperto `TextFieldParser` `reader` e utilizzato per leggere da `C:\TestFolder1\test1.txt` .</span><span class="sxs-lookup"><span data-stu-id="3c6af-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 <span data-ttu-id="3c6af-112">`My.Application`consente di modificare le impostazioni cultura per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3c6af-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="3c6af-113">Nell'esempio seguente viene illustrato come è possibile chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="3c6af-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3c6af-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c6af-114">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [<span data-ttu-id="3c6af-115">Dipendenza di My dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="3c6af-115">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
