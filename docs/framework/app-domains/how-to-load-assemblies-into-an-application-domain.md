---
title: "Procedura: Caricare assembly in un dominio dell'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86b66d0a88864188d67aab19de67aaa857a06eaa
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053173"
---
# <a name="how-to-load-assemblies-into-an-application-domain"></a>Procedura: Caricare assembly in un dominio dell'applicazione
È possibile caricare un assembly in un dominio dell'applicazione in diversi modi. Il modo consigliato consiste nell'usare il metodo `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.Load%2A> della classe <xref:System.Reflection.Assembly?displayProperty=nameWithType>. Gli assembly possono essere caricati anche nei modi seguenti:  
  
- Il metodo <xref:System.Reflection.Assembly.LoadFrom%2A> della classe <xref:System.Reflection.Assembly> carica un assembly dopo aver specificato il percorso del file. Se gli assembly vengono caricati usando questo metodo viene usato un contesto di caricamento diverso.  
  
- I metodi <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> e <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> caricano un assembly nel contesto di sola reflection. Gli assembly caricati in questo contesto possono essere esaminati ma non eseguiti. In questo modo è possibile esaminare assembly destinati ad altre piattaforme. Vedere [Procedura: Caricare assembly nel contesto Reflection-Only](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
> [!NOTE]
> Il contesto di sola reflection è stata introdotto con .NET Framework versione 2.0.  
  
- Metodi come <xref:System.AppDomain.CreateInstance%2A> e <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> della classe <xref:System.AppDomain> possono caricare gli assembly in un dominio dell'applicazione.  
  
- Il metodo <xref:System.Type.GetType%2A> della classe <xref:System.Type> può caricare assembly.  
  
- Il metodo <xref:System.AppDomain.Load%2A> della classe <xref:System.AppDomain?displayProperty=nameWithType> può caricare assembly ma viene usato principalmente per l'interoperabilità COM. Non usarlo per caricare assembly in un dominio dell'applicazione diverso da quello da cui è chiamato.  
  
> [!NOTE]
> A partire da .NET Framework versione 2.0 il runtime non caricherà un assembly compilato con una versione di .NET Framework con numero di versione superiore a quello del runtime attualmente caricato. Questo vale per la combinazione dei componenti numero principale e numero secondario del numero di versione.  
  
 È possibile specificare la modalità di condivisione del codice con compilazione JIT degli assembly caricati tra i domini dell'applicazione. Per altre informazioni, vedere [Domini applicazione e assembly](application-domains.md#application-domains-and-assemblies).  
  
## <a name="example"></a>Esempio  
 Il codice seguente carica un assembly denominato "example.exe" o "example.dll" nel dominio dell'applicazione corrente, ottiene un tipo denominato `Example` dall'assembly, ottiene un metodo senza parametri denominato `MethodA` per il tipo ed esegue il metodo. Per una descrizione completa di come ottenere informazioni da un assembly caricato, vedere [Caricamento e uso dinamico dei tipi](../reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- [Programmazione con i domini dell'applicazione](application-domains.md#programming-with-application-domains)
- [Reflection](../reflection-and-codedom/reflection.md)
- [Uso dei domini dell'applicazione](use.md)
- [Procedura: Caricare assembly nel contesto Reflection-Only](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)
- [Domini applicazione e assembly](application-domains.md#application-domains-and-assemblies)
