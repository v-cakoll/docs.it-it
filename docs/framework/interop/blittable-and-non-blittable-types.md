---
title: tipi copiabili e non copiabili
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
ms.openlocfilehash: 816b854120f09efef69bd8ceb2d3650e5a8e7af0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123725"
---
# <a name="blittable-and-non-blittable-types"></a>tipi copiabili e non copiabili
La maggior parte dei tipi di dati ha una rappresentazione comune sia nella memoria gestita sia in quella non gestita e non richiede quindi una gestione particolare tramite il gestore di marshalling di interoperabilità. Questi tipi sono definiti *copiabili da BLT*, poiché non richiedono la conversione quando vengono passati tra codice gestito e codice non gestito.  
  
 Le strutture restituite dalle chiamate platform invoke devono essere tipi copiabili da BLT. Platform invoke non supporta strutture non copiabili da BLT come tipi restituiti.  
  
 I tipi dello spazio dei nomi <xref:System> elencati di seguito sono copiabili da BLT:  
  
- <xref:System.Byte?displayProperty=nameWithType>  
  
- <xref:System.SByte?displayProperty=nameWithType>  
  
- <xref:System.Int16?displayProperty=nameWithType>  
  
- <xref:System.UInt16?displayProperty=nameWithType>  
  
- <xref:System.Int32?displayProperty=nameWithType>  
  
- <xref:System.UInt32?displayProperty=nameWithType>  
  
- <xref:System.Int64?displayProperty=nameWithType>  
  
- <xref:System.UInt64?displayProperty=nameWithType>  
  
- <xref:System.IntPtr?displayProperty=nameWithType>  
  
- <xref:System.UIntPtr?displayProperty=nameWithType>  
  
- <xref:System.Single?displayProperty=nameWithType>  
  
- <xref:System.Double?displayProperty=nameWithType>  
  
 Sono copiabili da BLT anche i tipi complessi seguenti:  
  
- Matrici unidimensionali di tipi copiabili da BLT, come una matrice di integer. Non è tuttavia copiabile da BLT un tipo contenente una matrice variabile di tipi copiabili da BLT.  
  
- Tipi di valore formattati contenenti solo tipi copiabili da BLT (e classi, se sottoposti a marshalling come tipi formattati). Per altre informazioni sui tipi di valore formattati, vedere [marshalling predefinito per i tipi di valore](default-marshaling-behavior.md#default-marshaling-for-value-types).  
  
 Non sono copiabili da BLT i riferimenti a oggetti, incluse le matrici di riferimenti a oggetti che invece sono copiabili da BLT. È possibile, ad esempio, definire una struttura copiabile da BLT, ma non un tipo copiabile da BLT contenente una matrice di riferimenti alla struttura.  
  
 Per motivi di ottimizzazione, le matrici di tipi e classi copiabili da BLT contenenti solo membri copiabili da BLT vengono [bloccate](copying-and-pinning.md) e non copiate durante il marshalling. Quando il chiamante e il chiamato si trovano nello stesso apartment, può sembrare che il marshalling di questi tipi venga eseguito come parametri In/Out. Il marshalling di questi tipi, in realtà, viene eseguito come parametri In ed è necessario applicare gli attributi <xref:System.Runtime.InteropServices.InAttribute> e <xref:System.Runtime.InteropServices.OutAttribute> se si vuole eseguire il marshalling dell'argomento come parametro In/Out.  
  
 Alcuni tipi di dati gestiti richiedono una rappresentazione diversa in un ambiente non gestito. Questi tipi di dati non copiabili da BLT devono essere convertiti in un formato di cui è possibile eseguire il marshalling. Le stringhe gestite, ad esempio, sono tipi non copiabili da BLT perché devono essere convertite in oggetti stringa prima di poter eseguire il marshalling.  
  
 Nella tabella seguente sono elencati i tipi non copiabili da BLT dello spazio dei nomi <xref:System>. Anche i [delegati](default-marshaling-behavior.md#default-marshaling-for-delegates), ossia le strutture di dati che fanno riferimento a un metodo statico o a un'istanza di classe, non sono copiabili da BLT.  
  
|Tipi non copiabili da BLT|Descrizione|  
|-------------------------|-----------------|  
|[System.Array](default-marshaling-for-arrays.md)|Viene convertito in una matrice di tipo C o in `SAFEARRAY`.|  
|[System. Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))|Viene convertito in un valore a 1, 2 o 4 byte con `true` pari a 1 o -1.|  
|[System. Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))|Viene convertito in un carattere Unicode o ANSI.|  
|[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))|Viene convertito in un'interfaccia di classe.|  
|[System. Object](default-marshaling-for-objects.md)|Viene convertito in una variante o in un'interfaccia.|  
|[System.Mdarray](default-marshaling-for-arrays.md)|Viene convertito in una matrice di tipo C o in `SAFEARRAY`.|  
|[System. String](default-marshaling-for-strings.md)|Viene convertito in una stringa che termina con un riferimento Null o un BSTR.|  
|[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))|Viene convertito in una struttura con un layout a memoria fissa.|  
|[System.Szarray](default-marshaling-for-arrays.md)|Viene convertito in una matrice di tipo C o in `SAFEARRAY`.|  
  
 I tipi di classe e oggetto sono supportati solo dall'interoperabilità COM. Per i tipi corrispondenti in Visual Basic, C#, e C++, vedere [Panoramica della libreria di classi](../../standard/class-library-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Comportamento di marshalling predefinito](default-marshaling-behavior.md)
