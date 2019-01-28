---
title: "Procedura: Usare proprietà indicizzate nella programmazione dell'interoperabilità COM - Guida per programmatori C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 920b9ad28bb3bd26b7606fba12bdf2e042be49fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509857"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>Procedura: Usare proprietà indicizzate nella programmazione dell'interoperabilità COM (Guida per programmatori C#)
Le *proprietà indicizzate* migliorano l'uso delle proprietà COM dotate di parametri nella programmazione C#. Tali proprietà operano congiuntamente ad altre funzionalità di Visual C#, ad esempio gli [argomenti denominati e facoltativi](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), un nuovo tipo ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)) e le [informazioni sul tipo incorporate](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), per migliorare la programmazione di Microsoft Office.  
  
 Nelle versioni precedenti di C# i metodi sono accessibili come proprietà solo se il metodo `get` non dispone di parametri e il metodo `set` ha un unico parametro valore. Non tutte le proprietà COM soddisfano tuttavia tali restrizioni. Ad esempio, la proprietà <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> di Excel possiede una funzione di accesso `get` che richiede un parametro per il nome dell'intervallo. In passato, poiché non era possibile accedere direttamente alla proprietà `Range`, era necessario usare il metodo`get_Range`, come illustrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]  
  
 Le proprietà indicizzate consentono invece di scrivere quanto segue:  
  
 [!code-csharp[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]  
  
> [!NOTE]
>  Nell'esempio precedente viene usata anche la funzionalità degli [argomenti facoltativi](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), che consente di omettere `Type.Missing`.  
  
 Analogamente, per impostare il valore della proprietà `Value` di un oggetto <xref:Microsoft.Office.Interop.Excel.Range> in Visual C# 2008 e versioni precedenti, sono necessari due argomenti. Uno specifica un argomento per un parametro facoltativo che specifica il tipo del valore dell'intervallo. L'altro indica il valore per la proprietà `Value`. Queste tecniche vengono illustrate negli esempi riportati di seguito. Entrambe impostano il valore della cella A1 su `Name`.
  
 [!code-csharp[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]  
  
 Le proprietà indicizzate consentono invece di scrivere il codice riportato di seguito.  
  
 [!code-csharp[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]  
  
 Non è possibile creare proprietà indicizzate personalizzate. La funzionalità supporta solo l'utilizzo di proprietà indicizzate esistenti.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra un esempio completo. Per altre informazioni su come configurare un progetto che accede all'API di Office, vedere [Procedura: Accedere agli oggetti di interoperabilità di Office usando le funzionalità di Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
 [!code-csharp[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Argomenti denominati e facoltativi](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [dynamic](../../../csharp/language-reference/keywords/dynamic.md)
- [Uso del tipo dinamico](../../../csharp/programming-guide/types/using-type-dynamic.md)
- [Procedura: Usare argomenti denominati e facoltativi nella programmazione di Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [Procedura: Accedere agli oggetti di interoperabilità di Office usando le funzionalità di Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)
- [Procedura dettagliata: Programmazione Office](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
