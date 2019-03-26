---
title: 'Interoperabilità - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
  - COM interop
  - interoperability
  - 'platform invoke, accessing APIs with C#'
  - 'C# language, interoperability'
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
---
# <a name="interoperability-c-programming-guide"></a>Interoperabilità (Guida per programmatori C#)
L'interoperabilità consente di preservare e sfruttare appieno gli investimenti effettuati in codice non gestito. Il codice eseguito sotto il controllo del Common Language Runtime (CLR) è detto *codice gestito*, mentre quello eseguito all'esterno è detto *codice non gestito*. Esempi di codice non gestito sono i componenti COM, COM+, C++, i componenti ActiveX e le API Microsoft Windows.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] consente l'interoperabilità con il codice non gestito tramite i servizi platform invoke, lo spazio dei nomi <xref:System.Runtime.InteropServices>, l'interoperabilità C++ e l'interoperabilità COM.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Cenni preliminari sull'interoperabilità](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 Vengono descritti i metodi per l'interoperabilità tra codice C# gestito e non gestito.  
  
 [Procedura: Accedere agli oggetti di interoperabilità di Office usando le funzionalità di Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 Vengono descritte le funzionalità introdotte in Visual C# per facilitare la programmazione di Office.  
  
 [Procedura: Usare proprietà indicizzate nella programmazione dell'interoperabilità COM](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 Viene illustrato come usare le proprietà indicizzate per accedere alle proprietà COM con parametri.  
  
 [Procedura: Usare platform invoke per riprodurre un file audio](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 Viene descritto come usare i servizi platform invoke per riprodurre un file audio con estensione wav nel sistema operativo Windows.  
  
 [Procedura dettagliata: Programmazione Office](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 Viene illustrato come creare una cartella di lavoro di Excel o un documento di Word contenente un collegamento alla cartella di lavoro.  
  
 [Esempio di classe COM](../../../csharp/programming-guide/interop/example-com-class.md)  
 Viene illustrato come esporre una classe C# come oggetto COM.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Concetti di base](~/_csharplang/spec/unsafe-code.md) nella [Specifica del linguaggio C#](../../language-reference/language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Interoperabilità con codice non gestito](../../../../docs/framework/interop/index.md)
- [Procedura dettagliata: Programmazione Office](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
