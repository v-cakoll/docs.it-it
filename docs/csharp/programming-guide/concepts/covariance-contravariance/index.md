---
title: Covarianza e controvarianza (C#)
description: Informazioni sulla covarianza e la controvarianza e sul modo in cui incidono sulla compatibilità dell'assegnazione. Vedere un esempio di codice in cui vengono illustrate le differenze tra di essi.
ms.date: 07/20/2015
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
ms.openlocfilehash: 65c75029c27b6c9a5ddc96f01622b520e8698f55
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105701"
---
# <a name="covariance-and-contravariance-c"></a>Covarianza e controvarianza (C#)
In C#, covarianza e controvarianza abilitano la conversione implicita del riferimento per i tipi di matrice, i tipi delegati e gli argomenti di tipo generico. La covarianza mantiene la compatibilità dell'assegnazione e la controvarianza la inverte.  
  
 Il codice seguente illustra la differenza tra la compatibilità dell'assegnazione, covarianza e controvarianza.  
  
```csharp  
// Assignment compatibility.
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.
object obj = str;  
  
// Covariance.
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument
// is assigned to an object instantiated with a less derived type argument.
// Assignment compatibility is preserved.
IEnumerable<object> objects = strings;  
  
// Contravariance.
// Assume that the following method is in the class:
// static void SetObject(object o) { }
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument
// is assigned to an object instantiated with a more derived type argument.
// Assignment compatibility is reversed.
Action<string> actString = actObject;  
```  
  
 La covarianza per le matrici consente la conversione implicita di una matrice di un tipo più derivato in una matrice di un tipo meno derivato. Ma questa operazione non è indipendente dai tipi, come illustrato nell'esempio di codice seguente.  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 Il supporto di covarianza e controvarianza per i gruppi di metodi consente la corrispondenza delle firme del metodo con i tipi delegati. Ciò consente di assegnare ai delegati non solo i metodi con firme corrispondenti, ma anche i metodi che restituiscono più tipi derivati (covarianza) o accettano parametri con meno tipi derivati (controvarianza) rispetto a quelli specificati dal tipo delegato. Per altre informazioni, vedere [Varianza nei delegati (C#)](./variance-in-delegates.md) e [Uso della varianza nei delegati (C#)](./using-variance-in-delegates.md).  
  
 L'esempio di codice seguente illustra il supporto di covarianza e controvarianza per i gruppi di metodi.  
  
```csharp  
static object GetObject() { return null; }  
static void SetObject(object obj) { }  
  
static string GetString() { return ""; }  
static void SetString(string str) { }  
  
static void Test()  
{  
    // Covariance. A delegate specifies a return type as object,  
    // but you can assign a method that returns a string.  
    Func<object> del = GetString;  
  
    // Contravariance. A delegate specifies a parameter type as string,  
    // but you can assign a method that takes an object.  
    Action<string> del2 = SetObject;  
}  
```  
  
 In .NET Framework 4 e versioni successive, C# supporta la covarianza e la controvarianza nelle interfacce e nei delegati generici e consente la conversione implicita di parametri di tipo generico. Per altre informazioni, vedere [Varianza nelle interfacce generiche (C#)](./variance-in-generic-interfaces.md) e [Varianza nei delegati (C#)](./variance-in-delegates.md).  
  
 L'esempio di codice seguente illustra la conversione implicita del riferimento per le interfacce generiche.  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 Le interfacce o i delegati generici sono detti *varianti* se i relativi parametri generici vengono dichiarati come covarianti o controvarianti. C# consente di creare i propri delegati e interfacce varianti. Per altre informazioni, vedere [Creazione di interfacce generiche varianti (C#)](./creating-variant-generic-interfaces.md) e [Varianza nei delegati (C#)](./variance-in-delegates.md).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Varianza nelle interfacce generiche (C#)](./variance-in-generic-interfaces.md)|Illustra la covarianza e la controvarianza nelle interfacce generiche e fornisce un elenco di interfacce generiche variant in .NET Framework.|  
|[Creazione di interfacce generiche varianti (C#)](./creating-variant-generic-interfaces.md)|Spiega come creare interfacce varianti personalizzate.|  
|[Uso della varianza nelle interfacce per le raccolte generiche (C#)](./using-variance-in-interfaces-for-generic-collections.md)|Spiega come il supporto di covarianza e controvarianza nelle interfacce <xref:System.Collections.Generic.IEnumerable%601> e <xref:System.IComparable%601> consente di riutilizzare il codice.|  
|[Varianza nei delegati (C#)](./variance-in-delegates.md)|Illustra la covarianza e la controvarianza nei delegati generici e non generici e offre un elenco di delegati generici varianti in .NET Framework.|  
|[Uso della varianza nei delegati (C#)](./using-variance-in-delegates.md)|Spiega come usare il supporto di covarianza e controvarianza nei delegati non generici per la corrispondenza delle firme del metodo con i tipi delegati.|  
|[Uso della varianza per i delegati generici Func e Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)|Spiega come il supporto di covarianza e controvarianza nei delegati `Func` e `Action` consente di riutilizzare il codice.|
