---
title: 'Procedura: confrontare stringhe (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4837fa57c962cba841ffcc83c5bd4475a4faff0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-compare-strings-c-programming-guide"></a>Procedura: confrontare stringhe (Guida per programmatori C#)

Quando si confrontano stringhe, viene prodotto un risultato che indica che una delle stringhe è più grande dell'altra o che le due stringhe sono uguali. Le regole che determinano il risultato sono diverse a seconda che si esegua un *confronto ordinale* o un *confronto con distinzione delle impostazioni cultura*. È importante usare il tipo di confronto corretto per l'attività specifica.

 Usare i confronti ordinali di base quando è necessario confrontare o ordinare i valori di due stringhe indipendentemente dalle convenzioni linguistiche. Un confronto ordinale di base (`System.StringComparison.Ordinal`) distingue tra maiuscole e minuscole, il che significa che le due stringhe devono corrispondere esattamente carattere per carattere: "e" non è uguale a "E". Una variante usata di frequente è `System.StringComparison.OrdinalIgnoreCase`, che include la corrispondenza a "e" ed "E". `StringComparison.OrdinalIgnoreCase` viene spesso usato per confrontare i nomi di file, i nomi di percorso, i percorsi di rete e qualsiasi altra stringa il cui valore non cambia in base alle impostazioni locali del computer dell'utente. Per altre informazioni, vedere <xref:System.StringComparison?displayProperty=nameWithType>.

 I confronti con distinzione delle impostazioni cultura vengono in genere usati per confrontare e ordinare stringhe immesse dagli utenti finali, in quanto i caratteri e le convenzioni di ordinamento di tali stringhe possono variare a seconda delle impostazioni locali del computer dell'utente. Anche stringhe che contengono caratteri identici potrebbero essere ordinate in modo diverso a seconda delle impostazioni cultura del thread corrente.

> [!NOTE]
> Quando si confrontano stringhe, è opportuno usare i metodi che consentono di specificare in modo esplicito il tipo di confronto che si intende eseguire. In questo modo il codice risulta molto più gestibile e leggibile. Se possibile, usare gli overload dei metodi delle classi <xref:System.String?displayProperty=nameWithType> e <xref:System.Array?displayProperty=nameWithType> che accettano un parametro di enumerazione <xref:System.StringComparison> in modo che sia possibile specificare quale tipo di confronto eseguire. È consigliabile evitare di usare gli operatori `==` e `!=` quando si confrontano stringhe. Non usare neppure i metodi dell'istanza <xref:System.String.CompareTo%2A?displayProperty=nameWithType> perché nessuno degli overload accetta <xref:System.StringComparison>.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come confrontare correttamente stringhe i cui valori non cambiano in base alle impostazioni locali del computer dell'utente. Viene anche illustrata la funzionalità di *centralizzazione delle stringhe* di C#. Quando un programma dichiara due o più variabili di stringa identiche, il compilatore le archivia tutte nello stesso percorso. Chiamando il metodo <xref:System.Object.ReferenceEquals%2A> è possibile vedere che le due stringhe si riferiscono effettivamente allo stesso oggetto in memoria. Usare il metodo <xref:System.String.Copy%2A?displayProperty=nameWithType> per evitare la centralizzazione, come illustrato nell'esempio.

[!code-csharp[csProgGuideStrings#11](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#11)]

## <a name="example"></a>Esempio

L'esempio seguente illustra come confrontare le stringhe con la modalità preferita tramite i metodi <xref:System.String?displayProperty=nameWithType> che accettano un'enumerazione <xref:System.StringComparison>. Si noti che i metodi dell'istanza <xref:System.String.CompareTo%2A?displayProperty=nameWithType> non vengono usati in questo caso, perché nessuno degli overload accetta <xref:System.StringComparison>.

[!code-csharp[csProgGuideStrings#31](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#31)]

## <a name="example"></a>Esempio

L'esempio seguente illustra come ordinare e cercare le stringhe in una matrice con distinzione delle impostazioni cultura usando i metodi statici <xref:System.Array> che accettano un parametro <xref:System.StringComparer?displayProperty=nameWithType>.

[!code-csharp[csProgGuideStrings#32](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#32)]

Le classi Collection, ad esempio <xref:System.Collections.Hashtable?displayProperty=nameWithType>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>, e <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> contengono costruttori che accettano un parametro <xref:System.StringComparer?displayProperty=nameWithType> quando il tipo degli elementi o delle chiavi è `string`. In generale è necessario usare sempre questi costruttori, quando possibile, e specificare il parametro `Ordinal` o `OrdinalIgnoreCase`.

## <a name="see-also"></a>Vedere anche
 <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>  
 <xref:System.StringComparer?displayProperty=nameWithType>  
 [Stringhe](../../../csharp/programming-guide/strings/index.md)  
 [Confronto di stringhe](../../../standard/base-types/comparing.md)  
 [Globalizzazione e localizzazione di applicazioni](/visualstudio/ide/globalizing-and-localizing-applications)