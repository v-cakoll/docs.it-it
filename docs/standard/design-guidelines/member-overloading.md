---
title: Overload dei membri
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c77f08cd573dc40083718b783ae01233ca00766
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="member-overloading"></a>Overload dei membri
Overload dei membri prevede la creazione di due o più membri sullo stesso tipo che hanno lo stesso nome ma che differiscono solo per il numero o il tipo dei parametri. Ad esempio, di seguito, il `WriteLine` viene eseguito l'overload di metodo:  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Poiché solo i metodi, costruttori e le proprietà indicizzate possono avere parametri, solo i membri possono essere sottoposti a overload.  
  
 Eseguire l'overload è una delle tecniche più importanti per migliorare la leggibilità di librerie riutilizzabili usabilità e produttività. L'overload per il numero di parametri consente di fornire versioni più semplice di costruttori e metodi. L'overload del tipo di parametro consente di utilizzare lo stesso nome di membro per l'esecuzione di operazioni identico a un set selezionato di tipi diversi di membri.  
  
 **✓ SI** tenta di utilizzare nomi di parametro descrittivi per indicare il valore predefinito utilizzato dagli overload più breve.  
  
 **X evitare** arbitrariamente i nomi dei parametri in overload. Se un parametro in uno degli overload rappresenta lo stesso input di un parametro in un altro overload, tali parametri devono avere lo stesso nome.  
  
 **X evitare** incoerente nell'ordine dei parametri in membri di overload. I parametri con lo stesso nome verrà visualizzato nella stessa posizione in tutti gli overload.  
  
 **✓ SI** rendere virtuale solo l'overload più lunga (se estendibilità è obbligatoria). Gli overload più brevi devono semplicemente chiamare tramite un overload più lungo.  
  
 **X non** usare `ref` o `out` modificatori per eseguire l'overload di membri.  
  
 Alcuni linguaggi non è possibile risolvere le chiamate agli overload simile al seguente. Inoltre, tali overload in genere hanno una semantica completamente diversa e probabilmente non deve essere overload, ma due metodi distinti invece.  
  
 **X non** dispongono di overload con parametri nella stessa posizione e tipi simili ma con una semantica diversa.  
  
 **✓ SI** consentire `null` da passare per gli argomenti facoltativi.  
  
 **✓ SI** utilizzare l'overload dei membri anziché definire membri con argomenti predefiniti.  
  
 Argomenti predefiniti non sono conformi a CLS.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
