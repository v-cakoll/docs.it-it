---
title: Implementazione dei metodi nei controlli personalizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], method implementation
- custom controls [Windows Forms], overloading methods
- custom controls [Windows Forms], method implementation
- methods [Windows Forms]
- methods [Windows Forms], custom controls
ms.assetid: 35d14fca-4bb4-4a27-8211-1f7a98ea27de
ms.openlocfilehash: 38dcad25af31b87afc1cc6ef4f89a1f7903bc0ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012763"
---
# <a name="method-implementation-in-custom-controls"></a>Implementazione dei metodi nei controlli personalizzati
Un metodo viene implementato in un controllo nello stesso modo in cui avviene in qualsiasi altro componente.  
  
 In Visual Basic, se un metodo deve restituire un valore, viene implementato come `Public Function`, mentre se non deve restituire alcun valore, viene implementato come `Public Sub`. I metodi vengono dichiarati usando la sintassi seguente:  
  
```vb  
Public Function ConvertMatterToEnergy(Matter as Integer) As Integer  
   ' Conversion code goes here.  
End Function  
```  
  
 Poiché le funzioni restituiscono un valore, devono specificare un tipo restituito come Integer, String, Object e così via. È anche necessario specificare gli argomenti accettati dalle routine `Function` o `Sub`, se presenti.  
  
 A differenza di Visual Basic, C# non fa distinzione tra funzioni e routine. Un metodo può restituire un valore o il risultato `void`. La sintassi per dichiarare un metodo pubblico in C# è la seguente:  
  
```csharp  
public int ConvertMatterToEnergy(int matter)  
{  
   // Conversion code goes here.  
}  
```  
  
 Quando si dichiara un metodo, ove possibile dichiarare tutti gli argomenti come tipi di dati espliciti. È necessario dichiarare gli argomenti che accettano i riferimenti agli oggetti come tipi di classe specifici, ad esempio `As Widget` anziché `As Object`. In Visual Basic, l'impostazione predefinita `Option Strict` applica automaticamente questa regola.  
  
 Gli argomenti con tipo assegnato consentono di individuare molti errori degli sviluppatori al momento della compilazione, piuttosto che in fase di esecuzione. Il compilatore individua sempre gli errori, mentre i test in fase di esecuzione sono funzionali come la suite di test.  
  
## <a name="overloaded-methods"></a>Metodi di overload  
 Per consentire agli utenti del controllo di specificare diverse combinazioni di parametri in un metodo, fornire più overload del metodo mediante la dichiarazione esplicita dei tipi di dati usati. Evitare di creare parametri dichiarati `As Object` che possono contenere qualsiasi tipo di dati, perché questo può causare errori che non vengono individuati nei test.  
  
> [!NOTE]
>  Il tipo di dati universale in è `Object` anziché `Variant`. `Variant` è stato rimosso dal linguaggio.  
  
 Ad esempio, il metodo `Spin` di un ipotetico controllo `Widget` potrebbe consentire la specifica diretta della direzione e della velocità di rotazione oppure la specifica di un altro oggetto `Widget` da cui assorbire il momento angolare:  
  
```vb  
Overloads Public Sub Spin( _  
   ByVal SpinDirection As SpinDirectionsEnum, _  
   ByVal RevolutionsPerSecond As Double)  
   ' Implementation code here.  
End Sub  
Overloads Public Sub Spin(ByVal Driver As Widget) _  
   ' Implementation code here.  
End Sub  
```  
  
```csharp  
public void Spin(SpinDirectionsEnum spinDirection, double revolutionsPerSecond)  
{  
   // Implementation code here.  
}  
  
public void Spin(Widget driver)  
{  
   // Implementation code here.  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](../../../standard/events/index.md)
- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
