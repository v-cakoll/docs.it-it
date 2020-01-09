---
title: Overload dei membri
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
ms.openlocfilehash: e7decab042dd1ee36beacb18956e175196cd112c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709283"
---
# <a name="member-overloading"></a>Overload dei membri
L'overload dei membri significa creare due o più membri dello stesso tipo che differiscono solo per il numero o il tipo di parametri, ma hanno lo stesso nome. Nel codice seguente, ad esempio, il metodo `WriteLine` è sovraccarico:  
  
```csharp  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Poiché solo i metodi, i costruttori e le proprietà indicizzate possono avere parametri, è possibile eseguire l'overload solo dei membri.  
  
 L'overload è una delle tecniche più importanti per migliorare l'usabilità, la produttività e la leggibilità delle librerie riutilizzabili. L'overload sul numero di parametri rende possibile fornire versioni più semplici dei costruttori e dei metodi. L'overload del tipo di parametro consente di utilizzare lo stesso nome di membro per i membri che eseguono operazioni identiche su un set selezionato di tipi diversi.  
  
 **✓ DO** tenta di utilizzare nomi di parametro descrittivi per indicare il valore predefinito utilizzato dagli overload più breve.  
  
 **X AVOID** arbitrariamente i nomi dei parametri in overload. Se un parametro in un overload rappresenta lo stesso input di un parametro in un altro overload, i parametri devono avere lo stesso nome.  
  
 **X AVOID** incoerente nell'ordine dei parametri in membri di overload. I parametri con lo stesso nome devono essere visualizzati nella stessa posizione in tutti gli overload.  
  
 **✓ DO** rendere virtuale solo l'overload più lunga (se estendibilità è obbligatoria). Gli overload più brevi devono semplicemente eseguire una chiamata a un overload più lungo.  
  
 **X DO NOT** usare `ref` o `out` modificatori per eseguire l'overload di membri.  
  
 Alcuni linguaggi non possono risolvere le chiamate a overload come questo. Inoltre, questi overload in genere hanno una semantica completamente diversa e probabilmente non devono essere overload ma due metodi distinti.  
  
 **X DO NOT** dispongono di overload con parametri nella stessa posizione e tipi simili ma con una semantica diversa.  
  
 **✓ DO** consentire `null` da passare per gli argomenti facoltativi.  
  
 **✓ DO** utilizzare l'overload dei membri anziché definire membri con argomenti predefiniti.  
  
 Gli argomenti predefiniti non sono conformi a CLS.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
