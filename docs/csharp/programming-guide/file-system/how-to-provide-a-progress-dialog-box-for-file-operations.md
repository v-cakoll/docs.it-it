---
title: 'Procedura: fornire una finestra di dialogo dello stato di avanzamento per operazioni su file (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0ac68b5aa6014db87b4f7a269ef73d0608371bd8
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="64949-102">Procedura: fornire una finestra di dialogo dello stato di avanzamento per operazioni su file (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="64949-102">How to: Provide a Progress Dialog Box for File Operations (C# Programming Guide)</span></span>
<span data-ttu-id="64949-103">È possibile fornire una finestra di dialogo standard che mostra lo stato di avanzamento delle operazioni sui file in Windows se si usa il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> nello spazio dei nomi <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="64949-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="64949-104">Per aggiungere un riferimento in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="64949-104">To add a reference in Visual Studio</span></span>  
  
1.  <span data-ttu-id="64949-105">Nella barra dei menu scegliere **Progetto**, **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="64949-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="64949-106">Verrà visualizzata la finestra di dialogo **Gestione riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="64949-106">The **Reference Manager** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="64949-107">Nell'area **Assembly** scegliere **Framework** se non è già stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="64949-107">In the **Assemblies** area, choose**Framework** if it isn’t already chosen.</span></span>  
  
3.  <span data-ttu-id="64949-108">Nell'elenco di nomi selezionare la casella di controllo **Microsoft.VisualBasic** e scegliere il pulsante **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="64949-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64949-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="64949-109">Example</span></span>  
 <span data-ttu-id="64949-110">Il codice seguente consente di copiare la directory che viene specificata da `sourcePath` nella directory specificata da `destinationPath`.</span><span class="sxs-lookup"><span data-stu-id="64949-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="64949-111">Questo codice specifica anche una finestra di dialogo standard che indica la quantità stimata di tempo rimanente per il completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="64949-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="64949-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64949-112">See Also</span></span>  
 [<span data-ttu-id="64949-113">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="64949-113">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
