---
title: Interoperabilità - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: 3a70d2ae077552bab536e96367cab0fda1661310
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712052"
---
# <a name="interoperability-c-programming-guide"></a>Interoperabilità (Guida per programmatori C#)
L'interoperabilità consente di preservare e sfruttare appieno gli investimenti effettuati in codice non gestito. Il codice eseguito sotto il controllo del Common Language Runtime (CLR) è detto *codice gestito*, mentre quello eseguito all'esterno è detto *codice non gestito*. Esempi di codice non gestito sono i componenti COM, COM+, C++, i componenti ActiveX e le API Microsoft Windows.  
  
 .NET Framework consente l'interoperabilità con il codice non gestito tramite i servizi platform invoke, lo spazio dei nomi <xref:System.Runtime.InteropServices>, l'interoperabilità C++ e l'interoperabilità COM.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Cenni preliminari sull'interoperabilità](./interoperability-overview.md)  
 Vengono descritti i metodi per l'interoperabilità tra codice C# gestito e non gestito.  
  
 [Come accedere agli oggetti di interoperabilità C# di Office usando le funzionalità](./how-to-access-office-onterop-objects.md)  
 Vengono descritte le funzionalità introdotte in Visual C# per facilitare la programmazione di Office.  
  
 [Come usare le proprietà indicizzate nella programmazione dell'interoperabilità COM](./how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 Viene illustrato come usare le proprietà indicizzate per accedere alle proprietà COM con parametri.  
  
 [Come usare platform invoke per riprodurre un file WAV](./how-to-use-platform-invoke-to-play-a-wave-file.md)  
 Viene descritto come usare i servizi platform invoke per riprodurre un file audio con estensione wav nel sistema operativo Windows.  
  
 [Procedura dettagliata: Programmazione di Office](./walkthrough-office-programming.md)  
 Viene illustrato come creare una cartella di lavoro di Excel o un documento di Word contenente un collegamento alla cartella di lavoro.  
  
 [Esempio di classe COM](./example-com-class.md)  
 Viene illustrato come esporre una classe C# come oggetto COM.  
  
## <a name="c-language-specification"></a>Specifica del linguaggio C#  

Per altre informazioni, vedere [Concetti di base](~/_csharplang/spec/unsafe-code.md) nella [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [Guida per programmatori C#](../index.md)
- [Interoperabilità con codice non gestito](../../../framework/interop/index.md)
- [Procedura dettagliata: Programmazione di Office](./walkthrough-office-programming.md)
