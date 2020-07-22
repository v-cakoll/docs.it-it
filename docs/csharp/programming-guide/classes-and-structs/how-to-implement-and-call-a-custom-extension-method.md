---
title: Come implementare e chiamare un metodo di estensione personalizzato-Guida per programmatori C#
description: Informazioni su come implementare metodi di estensione per qualsiasi tipo .NET. Il codice client può usare i metodi aggiungendo un riferimento a una DLL e aggiungendo una direttiva using.
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: 7856e78713648a42d1c961f50f7e83f2f7ef05b7
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865060"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a>Come implementare e chiamare un metodo di estensione personalizzato (Guida per programmatori C#)
Questo argomento illustra come implementare metodi di estensione personali per qualsiasi tipo .NET. Il codice client può usare i metodi di estensione aggiungendo un riferimento alla DLL che li contiene, e aggiungendo una direttiva [using](../../language-reference/keywords/using-directive.md) che specifica lo spazio dei nomi in cui vengono definiti i metodi di estensione.  
  
## <a name="to-define-and-call-the-extension-method"></a>Per definire e chiamare il metodo di estensione  
  
1. Definire una [classe](./static-classes-and-static-class-members.md) statica per contenere il metodo di estensione.  
  
     La classe deve essere visibile al codice client. Per altre informazioni sulle regole di accessibilità, vedere [Modificatori di accesso](./access-modifiers.md).  
  
2. Implementare il metodo di estensione come metodo statico con almeno la stessa visibilità della classe che lo contiene.  
  
3. Il primo parametro del metodo specifica il tipo su cui il metodo opera e deve essere preceduto dal modificatore [this](../../language-reference/keywords/this.md).  
  
4. Nel codice chiamante, aggiungere una direttiva `using` per specificare lo [spazio dei nomi](../../language-reference/keywords/namespace.md) che contiene la classe del metodo di estensione.  
  
5. Chiamare i metodi come se fossero metodi di istanza sul tipo.  
  
     Si noti che il primo parametro non viene specificato tramite la chiamata di codice, poiché rappresenta il tipo su cui viene applicato l'operatore e il compilatore conosce già il tipo dell'oggetto. È sufficiente specificare gli argomenti per i parametri da 2 a `n`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente un metodo di estensione denominato `WordCount` viene implementato nella classe `CustomExtensions.StringExtension`. Il metodo opera sulla classe <xref:System.String>, che viene specificata come primo parametro del metodo. Lo spazio dei nomi `CustomExtensions` viene importato nello spazio dei nomi dell'applicazione e il metodo viene chiamato all'interno del metodo `Main`.  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="net-security"></a>Sicurezza .NET  
 I metodi di estensione non presentano vulnerabilità di protezione specifiche. Non possono mai essere usati per rappresentare metodi esistenti su un tipo, perché tutti i conflitti di nomi vengono risolti a favore dell'istanza o del metodo statico definito dal tipo stesso. I metodi di estensione non possono accedere ai dati privati nella classe estesa.  
  
## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../index.md)
- [Metodi di estensione](./extension-methods.md)
- [LINQ (Language-Integrated Query)](../../linq/linq-in-csharp.md)
- [Classi statiche e membri di classi statiche](./static-classes-and-static-class-members.md)
- [protected](../../language-reference/keywords/protected.md)
- [interno](../../language-reference/keywords/internal.md)
- [pubblico](../../language-reference/keywords/public.md)
- [Questo](../../language-reference/keywords/this.md)
- [namespace](../../language-reference/keywords/namespace.md)
