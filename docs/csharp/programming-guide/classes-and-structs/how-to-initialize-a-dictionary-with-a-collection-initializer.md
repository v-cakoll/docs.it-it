---
title: 'Procedura: Inizializzare un dizionario con un inizializzatore di raccolta (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: 41d6a9934daaa1274901e20de58cfd480c904bfa
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="3a22a-102">Procedura: Inizializzare un dizionario con un inizializzatore di raccolta (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3a22a-102">How to: Initialize a Dictionary with a Collection Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="3a22a-103">Il metodo relativo <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> accetta due parametri, uno per la chiave e uno per il valore.</span><span class="sxs-lookup"><span data-stu-id="3a22a-103">A <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="3a22a-104">Per inizializzare un <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add\` o qualsiasi raccolta il cui metodo accetta più parametri, racchiudere tra parentesi ogni set di parametri, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3a22a-104">To initialize a <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add\` method takes multiple parameters, enclose each set of parameters in braces as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a22a-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a22a-105">Example</span></span>  
 <span data-ttu-id="3a22a-106">Nell'esempio seguente viene visualizzato <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName\`.</span><span class="sxs-lookup"><span data-stu-id="3a22a-106">In the following code example, a <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName\`.</span></span>  
  
 <span data-ttu-id="3a22a-107">[!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3a22a-107">[!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]</span></span>  
  
 <span data-ttu-id="3a22a-108">Si noti che vi sono due coppie di parentesi graffe in ogni elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="3a22a-108">Note the two pairs of braces in each element of the collection.</span></span> <span data-ttu-id="3a22a-109">Le parentesi più interne racchiudono l'inizializzatore di oggetto per `StudentName`, quelle più esterne racchiudono l'inizializzatore per la coppia chiave/valore che verrà aggiunta a `students`<xref:System.Collections.Generic.Dictionary\`2>.</span><span class="sxs-lookup"><span data-stu-id="3a22a-109">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students`<xref:System.Collections.Generic.Dictionary\`2>.</span></span> <span data-ttu-id="3a22a-110">Infine, tutto l'inizializzatore di insieme per il dizionario è racchiuso tra parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="3a22a-110">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a22a-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3a22a-111">Compiling the Code</span></span>  
 <span data-ttu-id="3a22a-112">Per eseguire questo codice, copiare e incollare la classe in un progetto di applicazione console di Visual C# creato in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a22a-112">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="3a22a-113">Per impostazione predefinita, questo progetto usa la versione 3.5 di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], e ha un riferimento a System.Core.dll e una direttiva using per System.Linq.</span><span class="sxs-lookup"><span data-stu-id="3a22a-113">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a using directive for System.Linq.</span></span> <span data-ttu-id="3a22a-114">Se uno o più di questi requisiti non è presente nel progetto, è possibile aggiungerlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="3a22a-114">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="3a22a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a22a-115">See Also</span></span>  
 <span data-ttu-id="3a22a-116">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3a22a-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="3a22a-117">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="3a22a-117">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

