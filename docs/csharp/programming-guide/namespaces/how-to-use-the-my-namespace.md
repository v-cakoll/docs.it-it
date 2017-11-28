---
title: 'Procedura: utilizzare lo spazio dei nomi My (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f3564c594a5fbb9bd05a956e5c12bbb173d2db51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a><span data-ttu-id="345b7-102">Procedura: utilizzare lo spazio dei nomi My (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="345b7-102">How to: Use the My Namespace (C# Programming Guide)</span></span>
<span data-ttu-id="345b7-103">Lo spazio dei nomi <xref:Microsoft.VisualBasic.MyServices> (`My` in Visual Basic) consente di accedere in modo semplice e intuitivo a numerose classi .NET Framework, permettendo di scrivere codice che interagisce con il computer, l'applicazione, le impostazioni, le risorse e così via.</span><span class="sxs-lookup"><span data-stu-id="345b7-103">The <xref:Microsoft.VisualBasic.MyServices> namespace (`My` in Visual Basic) provides easy and intuitive access to a number of .NET Framework classes, enabling you to write code that interacts with the computer, application, settings, resources, and so on.</span></span> <span data-ttu-id="345b7-104">Anche se originariamente progettato per l'uso con Visual Basic, lo spazio dei nomi `MyServices` può essere usato nelle applicazioni C#.</span><span class="sxs-lookup"><span data-stu-id="345b7-104">Although originally designed for use with Visual Basic, the `MyServices` namespace can be used in C# applications.</span></span>  
  
 <span data-ttu-id="345b7-105">Per altre informazioni sull'uso dello spazio dei nomi `MyServices` da Visual Basic, vedere [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md) (Sviluppo con My).</span><span class="sxs-lookup"><span data-stu-id="345b7-105">For more information about using the `MyServices` namespace from Visual Basic, see [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md).</span></span>  
  
## <a name="adding-a-reference"></a><span data-ttu-id="345b7-106">Aggiunta di un riferimento</span><span class="sxs-lookup"><span data-stu-id="345b7-106">Adding a Reference</span></span>  
 <span data-ttu-id="345b7-107">Prima di poter usare le classi `MyServices` nella soluzione, è necessario aggiungere un riferimento alla libreria di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="345b7-107">Before you can use the `MyServices` classes in your solution, you must add a reference to the Visual Basic library.</span></span>  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a><span data-ttu-id="345b7-108">Per aggiungere un riferimento alla libreria di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="345b7-108">To add a reference to the Visual Basic library</span></span>  
  
1.  <span data-ttu-id="345b7-109">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="345b7-109">In **Solution Explorer**, right-click the **References** node, and select **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="345b7-110">Nella finestra di dialogo **Riferimenti** visualizzata scorrere l'elenco e selezionare Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="345b7-110">When the **References** dialog box appears, scroll down the list, and select Microsoft.VisualBasic.dll.</span></span>  
  
     <span data-ttu-id="345b7-111">È anche possibile includere la riga seguente nella sezione `using` all'inizio del programma.</span><span class="sxs-lookup"><span data-stu-id="345b7-111">You might also want to include the following line in the `using` section at the start of your program.</span></span>  
  
     [!code-csharp[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="345b7-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="345b7-112">Example</span></span>  
 <span data-ttu-id="345b7-113">Questo esempio chiama diversi metodi statici contenuti nello spazio dei nomi `MyServices`.</span><span class="sxs-lookup"><span data-stu-id="345b7-113">This example calls various static methods contained in the `MyServices` namespace.</span></span> <span data-ttu-id="345b7-114">Per compilare questo codice, è necessario aggiungere al progetto un riferimento a Microsoft.VisualBasic.DLL.</span><span class="sxs-lookup"><span data-stu-id="345b7-114">For this code to compile, a reference to Microsoft.VisualBasic.DLL must be added to the project.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]  
  
 <span data-ttu-id="345b7-115">Non tutte le classi incluse nello spazio dei nomi `MyServices` possono essere chiamate da un'applicazione C#. La classe <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>, ad esempio, non è compatibile.</span><span class="sxs-lookup"><span data-stu-id="345b7-115">Not all the classes in the `MyServices` namespace can be called from a C# application: for example, the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> class is not compatible.</span></span> <span data-ttu-id="345b7-116">In questo caso specifico è possibile usare i metodi statici inclusi in <xref:Microsoft.VisualBasic.FileIO.FileSystem> e contenuti anche nel file VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="345b7-116">In this particular case, the static methods that are part of <xref:Microsoft.VisualBasic.FileIO.FileSystem>, which are also contained in VisualBasic.dll, can be used instead.</span></span> <span data-ttu-id="345b7-117">Ecco ad esempio come usare uno di questi metodi per duplicare una directory:</span><span class="sxs-lookup"><span data-stu-id="345b7-117">For example, here is how to use one such method to duplicate a directory:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="345b7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="345b7-118">See Also</span></span>  
 [<span data-ttu-id="345b7-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="345b7-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="345b7-120">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="345b7-120">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
 [<span data-ttu-id="345b7-121">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="345b7-121">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)
