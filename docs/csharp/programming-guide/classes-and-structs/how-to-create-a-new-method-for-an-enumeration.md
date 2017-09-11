---
title: 'Procedura: creare un nuovo metodo per una enumerazione (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
caps.latest.revision: 7
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
ms.openlocfilehash: 22feed835b8a868cca2839467a8e5cc7118db39a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="a192a-102">Procedura: creare un nuovo metodo per una enumerazione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a192a-102">How to: Create a New Method for an Enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="a192a-103">È possibile usare metodi di estensione per aggiungere la funzionalità specifica di un particolare tipo enum.</span><span class="sxs-lookup"><span data-stu-id="a192a-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a192a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a192a-104">Example</span></span>  
 <span data-ttu-id="a192a-105">Nell'esempio seguente, l'enumerazione `Grades` rappresenta il voto che uno studente potrebbe ricevere in un corso.</span><span class="sxs-lookup"><span data-stu-id="a192a-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="a192a-106">Il metodo di estensione denominato `Passing` viene aggiunto al tipo `Grades` in modo che ogni istanza di tale tipo ora "sa" se rappresenta un voto sufficiente oppure no.</span><span class="sxs-lookup"><span data-stu-id="a192a-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 <span data-ttu-id="a192a-107">[!code-cs[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a192a-107">[!code-cs[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]</span></span>  
  
 <span data-ttu-id="a192a-108">Si noti che la classe `Extensions` contiene anche una variabile statica aggiornata in modo dinamico e che il valore restituito dal metodo di estensione riflette il valore corrente di tale variabile.</span><span class="sxs-lookup"><span data-stu-id="a192a-108">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="a192a-109">Ciò dimostra che dietro le quinte i metodi di estensione vengono chiamati direttamente per la classe statica nella quale sono definiti.</span><span class="sxs-lookup"><span data-stu-id="a192a-109">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a192a-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a192a-110">Compiling the Code</span></span>  
 <span data-ttu-id="a192a-111">Per eseguire questo codice, copiarlo e incollarlo nel progetto di applicazione console di Visual C# creato in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a192a-111">To run this code, copy and paste it into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="a192a-112">Per impostazione predefinita, questo progetto usa la versione 3.5 di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] e contiene un riferimento a System.Core.dll e una direttiva `using` per System.Linq.</span><span class="sxs-lookup"><span data-stu-id="a192a-112">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="a192a-113">Se uno o più di questi requisiti non sono presenti nel progetto, è possibile aggiungerli manualmente.</span><span class="sxs-lookup"><span data-stu-id="a192a-113">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="a192a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a192a-114">See Also</span></span>  
 <span data-ttu-id="a192a-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a192a-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="a192a-116">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="a192a-116">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)

