---
title: Proprietà implementate automaticamente - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 212fdde3a5ecc8b0a43e33bec3537bd57b1387e9
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419411"
---
# <a name="auto-implemented-properties-c-programming-guide"></a>Proprietà implementate automaticamente (Guida per programmatori C#)
In C# 3.0 e versioni successive, le proprietà implementate automaticamente rendono più concisa la dichiarazione di proprietà quando nelle funzioni di accesso della proprietà non è necessaria alcuna logica aggiuntiva. Consentono inoltre al codice client di creare oggetti. Quando si dichiara una proprietà come mostrato nel seguente esempio, il compilatore crea un campo sottostante privato anonimo accessibile solo tramite le funzioni di accesso `get` e `set` della proprietà.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra una classe semplice con alcune proprietà implementate automaticamente:  
  
 [!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  
  
 In C# 6 e versioni successive, è possibile inizializzare le proprietà implementate automaticamente in modo simile ai campi:  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 La classe mostrata nell'esempio precedente è modificabile. Il codice client può modificare i valori negli oggetti dopo che sono stati creati. Nelle classi complesse che contengono un comportamento significativo (metodi) oltre ai dati, spesso è necessario disporre di proprietà pubbliche. Tuttavia, per le classi o gli struct di piccole dimensioni che incapsulano solo un set di valori (dati) e non hanno comportamenti oppure hanno comportamenti limitati, è consigliabile rendere gli oggetti non modificabili dichiarando la funzione di accesso set come [private](../../language-reference/keywords/private.md) (non modificabile dai consumer) o dichiarando solo una funzione di accesso get (non modificabile, tranne che nel costruttore).  Per altre informazioni, vedere [Procedura: Implementare una classe leggera con proprietà implementate automaticamente](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).  
  
## <a name="see-also"></a>Vedere anche

- [Proprietà](./properties.md)
- [Modificatori](/dotnet/csharp/language-reference/keywords)
