---
title: Proprietà implementate automaticamente - Guida per programmatori C#
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 989266bfc2de9bd5ce2948f09a2b9f19dd2c782e
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628293"
---
# <a name="auto-implemented-properties-c-programming-guide"></a>Proprietà implementate automaticamente (Guida per programmatori C#)

In C# 3.0 e versioni successive, le proprietà implementate automaticamente rendono più concisa la dichiarazione di proprietà quando nelle funzioni di accesso della proprietà non è necessaria alcuna logica aggiuntiva. Consentono inoltre al codice client di creare oggetti. Quando si dichiara una proprietà come mostrato nel seguente esempio, il compilatore crea un campo sottostante privato anonimo accessibile solo tramite le funzioni di accesso `get` e `set` della proprietà.
  
## <a name="example"></a>Esempio

L'esempio seguente mostra una classe semplice con alcune proprietà implementate automaticamente:  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

Non è possibile dichiarare proprietà implementate automaticamente nelle interfacce. Le proprietà implementate automaticamente dichiarano un campo sottostante istanza privata e le interfacce non possono dichiarare campi di istanza. La dichiarazione di una proprietà in un'interfaccia senza la definizione di un corpo dichiara una proprietà con funzioni di accesso che devono essere implementate da ogni tipo che implementa tale interfaccia.

In C# 6 e versioni successive, è possibile inizializzare le proprietà implementate automaticamente in modo simile ai campi:  
 
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
 
La classe mostrata nell'esempio precedente è modificabile. Il codice client può modificare i valori negli oggetti dopo la creazione. Nelle classi complesse che contengono un comportamento significativo (metodi) e i dati, spesso è necessario disporre di proprietà pubbliche. Tuttavia, per le classi o gli struct di piccole dimensioni che incapsulano solo un set di valori (dati) e non hanno comportamenti oppure hanno comportamenti limitati, è consigliabile rendere gli oggetti non modificabili dichiarando la funzione di accesso set come [private](../../language-reference/keywords/private.md) (non modificabile dai consumer) o dichiarando solo una funzione di accesso get (non modificabile, tranne che nel costruttore).  Per ulteriori informazioni, vedere [come implementare una classe Lightweight con proprietà implementate automaticamente](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).

## <a name="see-also"></a>Vedere anche

- [Proprietà](./properties.md)
- [Modificatori](/dotnet/csharp/language-reference/keywords)
