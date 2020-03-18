---
title: Generics e reflection - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], reflection
- reflection [C#], generic types
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
ms.openlocfilehash: 4893bf5ebe73988bb6535cc2a85591ff0dde6ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712169"
---
# <a name="generics-and-reflection-c-programming-guide"></a>Generics e reflection (Guida per programmatori C#)
Poiché Common Language Runtime (CLR) ha accesso alle informazioni sui tipi generici in fase di esecuzione, è possibile usare il processo di reflection per ottenere informazioni sui tipi generici, analogamente a quanto avviene per i tipi non generici. Per altre informazioni, vedere [Generics nel runtime](./generics-in-the-run-time.md).  
  
 In .NET Framework 2.0, per abilitare le informazioni di runtime per i tipi generici sono stati aggiunti nuovi membri alla classe <xref:System.Type>. Vedere la documentazione su queste classi per altre informazioni su come usare tali metodi e proprietà. Anche lo spazio dei nomi <xref:System.Reflection.Emit> contiene nuovi membri che supportano i generics. Vedere [Procedura: Definire un tipo generico tramite reflection emit](../../../framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md).  
  
 Per un elenco delle condizioni invariabili relative ai termini usati dal processo di reflection generico, vedere i commenti sulla proprietà <xref:System.Type.IsGenericType%2A>.  
  
|Nome del membro System. Type|Descrizione|  
|-----------------------------|-----------------|  
|<xref:System.Type.IsGenericType%2A>|Restituisce true se un tipo è generico.|  
|<xref:System.Type.GetGenericArguments%2A>|Restituisce una matrice di oggetti `Type` che rappresentano gli argomenti di tipo specificati per un tipo costruito oppure i parametri di tipo di una definizione di un tipo generico.|  
|<xref:System.Type.GetGenericTypeDefinition%2A>|Restituisce la definizione di un tipo generico sottostante per il tipo costruito corrente.|  
|<xref:System.Type.GetGenericParameterConstraints%2A>|Restituisce una matrice di oggetti `Type` che rappresentano i vincoli sul parametro di tipo generico corrente.|  
|<xref:System.Type.ContainsGenericParameters%2A>|Restituisce true se il tipo o uno dei tipi o dei metodi che lo contengono comprendono parametri di tipo per cui non sono stati indicati tipi specifici.|  
|<xref:System.Type.GenericParameterAttributes%2A>|Ottiene una combinazione di flag `GenericParameterAttributes` che descrivono i vincoli speciali del parametro di tipo generico corrente.|  
|<xref:System.Type.GenericParameterPosition%2A>|Per un oggetto `Type` che rappresenta un parametro di tipo, ottiene la posizione del parametro di tipo nell'elenco dei parametri di tipo della definizione di un tipo generico o della definizione di un metodo generico che ha dichiarato il parametro di tipo.|  
|<xref:System.Type.IsGenericParameter%2A>|Ottiene un valore che indica se l'oggetto `Type` corrente rappresenta un parametro di tipo di una definizione di un tipo o metodo generico.|  
|<xref:System.Type.IsGenericTypeDefinition%2A>|Ottiene un valore che indica se la classe <xref:System.Type> corrente rappresenta una definizione di tipo generico, da cui è possibile costruire altri tipi generici. Restituisce true se il tipo rappresenta la definizione di un tipo generico.|  
|<xref:System.Type.DeclaringMethod%2A>|Restituisce il metodo generico che ha definito il parametro di tipo generico corrente oppure Null se il parametro di tipo non è stato definito da un metodo generico.|  
|<xref:System.Type.MakeGenericType%2A>|Sostituisce gli elementi di una matrice di tipi ai parametri di tipo della definizione di tipo generico corrente e restituisce un oggetto <xref:System.Type> che rappresenta il tipo costruito risultante.|  
  
 Inoltre, i membri della classe <xref:System.Reflection.MethodInfo> abilitano le informazioni di runtime per i tipi generici. Per un elenco delle condizioni invariabili relative ai termini usati dal processo di reflection per i metodi generici, vedere le note sulla proprietà <xref:System.Reflection.MethodBase.IsGenericMethod%2A>.  
  
|System.Reflection.MemberInfo Member Name|Descrizione|  
|----------------------------------------------|-----------------|  
|<xref:System.Reflection.MethodBase.IsGenericMethod%2A>|Restituisce true se un metodo è generico.|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|Restituisce una matrice di oggetti Type che rappresentano gli argomenti di tipo di un metodo generico costruito oppure i parametri di tipo di una definizione di un metodo generico.|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|Restituisce la definizione di un metodo generico sottostante per il metodo costruito corrente.|  
|<xref:System.Reflection.MethodBase.ContainsGenericParameters%2A>|Restituisce true se il metodo o uno dei tipi che lo contengono comprendono parametri di tipo per cui non sono stati indicati tipi specifici.|  
|<xref:System.Reflection.MethodBase.IsGenericMethodDefinition%2A>|Restituisce true se l'oggetto <xref:System.Reflection.MethodInfo> corrente rappresenta la definizione di un metodo generico.|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|Sostituisce con gli elementi di una matrice di tipi i parametri di tipo della definizione di metodo generica corrente e restituisce un oggetto <xref:System.Reflection.MethodInfo> che rappresenta il metodo costruito risultante.|  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Generics](./index.md)
- [Reflection e tipi generici](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- [Generics](../../../standard/generics/index.md)
