---
title: Come usare le proprietà indicizzate nella programmazione dell'interoperabilità COM- C# Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 864e2274f0e0e79b4843e0bb67b5c4384eac8588
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712065"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>Come utilizzare le proprietà indicizzate nella programmazione dell'interoperabilità COM (C# guida per programmatori)
Le *proprietà indicizzate* migliorano l'uso delle proprietà COM dotate di parametri nella programmazione C#. Tali proprietà operano congiuntamente ad altre funzionalità di Visual C#, ad esempio gli [argomenti denominati e facoltativi](../classes-and-structs/named-and-optional-arguments.md), un nuovo tipo ([dynamic](../../language-reference/builtin-types/reference-types.md)) e le [informazioni sul tipo incorporate](../../../standard/assembly/embed-types-visual-studio.md), per migliorare la programmazione di Microsoft Office.  
  
 Nelle versioni precedenti di C# i metodi sono accessibili come proprietà solo se il metodo `get` non dispone di parametri e il metodo `set` ha un unico parametro valore. Non tutte le proprietà COM soddisfano tuttavia tali restrizioni. Ad esempio, la proprietà <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> di Excel possiede una funzione di accesso `get` che richiede un parametro per il nome dell'intervallo. In passato, poiché non era possibile accedere direttamente alla proprietà `Range`, era necessario usare il metodo`get_Range`, come illustrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 Le proprietà indicizzate consentono invece di scrivere quanto segue:  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> Nell'esempio precedente viene usata anche la funzionalità degli [argomenti facoltativi](../classes-and-structs/named-and-optional-arguments.md), che consente di omettere `Type.Missing`.  
  
 Analogamente, per impostare il valore della proprietà `Value` di un oggetto <xref:Microsoft.Office.Interop.Excel.Range> in C# 3.0 e versioni precedenti, sono necessari due argomenti. Uno specifica un argomento per un parametro facoltativo che specifica il tipo del valore dell'intervallo. L'altro indica il valore per la proprietà `Value`. Queste tecniche vengono illustrate negli esempi riportati di seguito. Entrambe impostano il valore della cella A1 su `Name`.
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 Le proprietà indicizzate consentono invece di scrivere il codice riportato di seguito.  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 Non è possibile creare proprietà indicizzate personalizzate. La funzionalità supporta solo l'utilizzo di proprietà indicizzate esistenti.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra un esempio completo. Per altre informazioni su come configurare un progetto che accede all'API di Office, vedere [come accedere agli oggetti di interoperabilità di Office C# usando le funzionalità di](./how-to-access-office-onterop-objects.md).
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Argomenti denominati e facoltativi](../classes-and-structs/named-and-optional-arguments.md)
- [dynamic](../../language-reference/builtin-types/reference-types.md)
- [Uso del tipo dinamico](../types/using-type-dynamic.md)
- [Come usare gli argomenti denominati e facoltativi nella programmazione di Office](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [Come accedere agli oggetti di interoperabilità C# di Office usando le funzionalità](./how-to-access-office-onterop-objects.md)
- [Procedura dettagliata: Programmazione di Office](./walkthrough-office-programming.md)
