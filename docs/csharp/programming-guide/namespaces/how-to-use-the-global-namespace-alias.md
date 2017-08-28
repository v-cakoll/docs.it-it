---
title: 'Procedura: utilizzare l''alias dello spazio dei nomi globale (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
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
ms.openlocfilehash: 1252fc107d46b1d3a1cbef0a61708edc57253910
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a>Procedura: utilizzare l'alias dello spazio dei nomi globale (Guida per programmatori C#)
La possibilità di accedere a un membro nello [spazio dei nomi globale](../../../csharp/language-reference/keywords/namespace.md) è utile quando il membro può essere nascosto da un'altra entità con lo stesso nome.  
  
 Nel codice seguente, ad esempio, `Console` si risolve in `TestApp.Console` invece che nel tipo `Console` nello spazio dei nomi <xref:System>.  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 L'uso di `System.Console` causa comunque un errore perché lo spazio dei nomi `System` è nascosto dalla classe `TestApp.System`:  
  
 [!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 È tuttavia possibile evitare questo errore usando `global::System.Console`, come indicato di seguito:  
  
 [!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 Se l'identificatore di sinistra è `global`, la ricerca dell'identificatore di destra ha inizio dallo spazio dei nomi globale. La seguente dichiarazione fa ad esempio riferimento a `TestApp` come membro dello spazio globale.  
  
 [!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 Non è ovviamente consigliabile creare spazi dei nomi personali denominati `System` ed è improbabile trovare codice che include uno spazio dei nomi con tale nome. Nei progetti di grandi dimensioni è tuttavia molto probabile che si verifichi in qualche modo la duplicazione degli spazi dei nomi. In queste situazioni è possibile usare il qualificatore dello spazio dei nomi globale per specificare lo spazio dei nomi radice.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato lo spazio dei nomi `System` per includere la classe `TestClass`. Di conseguenza, è necessario usare `global::System.Console` per fare riferimento alla classe `System.Console`, nascosta dallo spazio dei nomi `System`. Viene inoltre usato l'alias `colAlias` per fare riferimento allo spazio dei nomi `System.Collections`. Di conseguenza, l'istanza di un oggetto <xref:System.Collections.Hashtable?displayProperty=fullName> è stata creata usando questo alias invece dello spazio dei nomi.  
  
 [!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
 **A 1**  
**B 2**  
**C 3**   
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Spazi dei nomi](../../../csharp/programming-guide/namespaces/index.md)   
 [. Operatore](../../../csharp/language-reference/operators/member-access-operator.md)   
 [Operatore ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)

