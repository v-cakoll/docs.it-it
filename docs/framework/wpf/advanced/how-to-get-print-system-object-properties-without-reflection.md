---
title: "Procedura: Ottenere le proprietà dell'oggetto del sistema di stampa senza reflection"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: b9ca7444b2c49f4563ff0d7baef8b2d250a7f331
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215274"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a>Procedura: Ottenere le proprietà dell'oggetto del sistema di stampa senza reflection
Uso della reflection per specificare i dettagli delle proprietà (e i tipi di tali proprietà) su un oggetto può rallentare le prestazioni dell'applicazione. Il <xref:System.Printing.IndexedProperties> dello spazio dei nomi fornisce un mezzo per ottenere queste informazioni con l'uso della reflection.  
  
## <a name="example"></a>Esempio  
 I passaggi per eseguire questa operazione sono i seguenti.  
  
1.  Creare un'istanza del tipo. Nell'esempio seguente, il tipo è il <xref:System.Printing.PrintQueue> tipo fornito con Microsoft .NET Framework, ma quasi identico codice dovrebbe funzionare per i tipi che derivano dal <xref:System.Printing.PrintSystemObject>.  
  
2.  Creare un <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> dalla proprietà del tipo <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>. Il <xref:System.Collections.DictionaryEntry.Value%2A> proprietà di ogni voce in questo dizionario è un oggetto di uno dei tipi derivati da <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
3.  Enumerare i membri del dizionario. Per ognuno di essi, procedere come segue.  
  
4.  Il valore di ogni voce per l'upcast <xref:System.Printing.IndexedProperties.PrintProperty> e usarlo per creare un <xref:System.Printing.IndexedProperties.PrintProperty> oggetto.  
  
5.  Ottenere il tipo dei <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> di ogni il <xref:System.Printing.IndexedProperties.PrintProperty> oggetto.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sulla stampa](printing-overview.md)
