---
title: Come implementare e chiamare un metodo di estensione personalizzato- C# Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: 7e2092a37c1f042a087e03f4a272139b585156c8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705600"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a>Come implementare e chiamare un metodo di estensione personalizzato (C# guida per programmatori)
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
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 I metodi di estensione non presentano vulnerabilità di protezione specifiche. Non possono mai essere usati per rappresentare metodi esistenti su un tipo, perché tutti i conflitti di nomi vengono risolti a favore dell'istanza o del metodo statico definito dal tipo stesso. I metodi di estensione non possono accedere ai dati privati nella classe estesa.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Metodi di estensione](./extension-methods.md)
- [LINQ (Language-Integrated Query)](../../linq/linq-in-csharp.md)
- [Classi statiche e membri di classi statiche](./static-classes-and-static-class-members.md)
- [protected](../../language-reference/keywords/protected.md)
- [internal](../../language-reference/keywords/internal.md)
- [public](../../language-reference/keywords/public.md)
- [this](../../language-reference/keywords/this.md)
- [namespace](../../language-reference/keywords/namespace.md)
