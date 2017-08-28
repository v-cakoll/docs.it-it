---
title: 'Procedura: utilizzare lo spazio dei nomi My (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 56577ff61c3f637c8e5a0969ae75d65d24ddaef7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a>Procedura: utilizzare lo spazio dei nomi My (Guida per programmatori C#)
Lo spazio dei nomi <xref:Microsoft.VisualBasic.MyServices> (`My` in Visual Basic) consente di accedere in modo semplice e intuitivo a numerose classi .NET Framework, permettendo di scrivere codice che interagisce con il computer, l'applicazione, le impostazioni, le risorse e così via. Anche se originariamente progettato per l'uso con Visual Basic, lo spazio dei nomi `MyServices` può essere usato nelle applicazioni C#.  
  
 Per altre informazioni sull'uso dello spazio dei nomi `MyServices` da Visual Basic, vedere [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md) (Sviluppo con My).  
  
## <a name="adding-a-reference"></a>Aggiunta di un riferimento  
 Prima di poter usare le classi `MyServices` nella soluzione, è necessario aggiungere un riferimento alla libreria di Visual Basic.  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a>Per aggiungere un riferimento alla libreria di Visual Basic  
  
1.  In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** e scegliere **Aggiungi riferimento**.  
  
2.  Nella finestra di dialogo **Riferimenti** visualizzata scorrere l'elenco e selezionare Microsoft.VisualBasic.dll.  
  
     È anche possibile includere la riga seguente nella sezione `using` all'inizio del programma.  
  
     [!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]  
  
## <a name="example"></a>Esempio  
 Questo esempio chiama diversi metodi statici contenuti nello spazio dei nomi `MyServices`. Per compilare questo codice, è necessario aggiungere al progetto un riferimento a Microsoft.VisualBasic.DLL.  
  
 [!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]  
  
 Non tutte le classi incluse nello spazio dei nomi `MyServices` possono essere chiamate da un'applicazione C#. La classe <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>, ad esempio, non è compatibile. In questo caso specifico è possibile usare i metodi statici inclusi in <xref:Microsoft.VisualBasic.FileIO.FileSystem> e contenuti anche nel file VisualBasic.dll. Ecco ad esempio come usare uno di questi metodi per duplicare una directory:  
  
 [!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Spazi dei nomi](../../../csharp/programming-guide/namespaces/index.md)   
 [Uso degli spazi dei nomi](../../../csharp/programming-guide/namespaces/using-namespaces.md)

