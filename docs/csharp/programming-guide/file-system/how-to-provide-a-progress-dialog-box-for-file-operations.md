---
title: 'Procedura: fornire una finestra di dialogo dello stato di avanzamento per operazioni su file (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: e93ce06a01046dfaf4465470ba7fdc687effa58d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47207403"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="910de-102">Procedura: fornire una finestra di dialogo dello stato di avanzamento per operazioni su file (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="910de-102">How to: Provide a Progress Dialog Box for File Operations (C# Programming Guide)</span></span>
<span data-ttu-id="910de-103">È possibile fornire una finestra di dialogo standard che mostra lo stato di avanzamento delle operazioni sui file in Windows se si usa il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> nello spazio dei nomi <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="910de-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="910de-104">Per aggiungere un riferimento in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="910de-104">To add a reference in Visual Studio</span></span>  
  
1.  <span data-ttu-id="910de-105">Nella barra dei menu scegliere **Progetto**, **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="910de-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="910de-106">Verrà visualizzata la finestra di dialogo **Gestione riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="910de-106">The **Reference Manager** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="910de-107">Nell'area **Assembly** scegliere **Framework** se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="910de-107">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
3.  <span data-ttu-id="910de-108">Nell'elenco di nomi selezionare la casella di controllo **Microsoft.VisualBasic** e scegliere il pulsante **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="910de-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="910de-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="910de-109">Example</span></span>  
 <span data-ttu-id="910de-110">Il codice seguente consente di copiare la directory che viene specificata da `sourcePath` nella directory specificata da `destinationPath`.</span><span class="sxs-lookup"><span data-stu-id="910de-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="910de-111">Questo codice specifica anche una finestra di dialogo standard che indica la quantità stimata di tempo rimanente per il completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="910de-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="910de-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="910de-112">See Also</span></span>

- [<span data-ttu-id="910de-113">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="910de-113">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
