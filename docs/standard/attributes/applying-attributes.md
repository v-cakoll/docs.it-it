---
title: Applicazione di attributi
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- attributes [.NET Framework], applying
ms.assetid: dd7604eb-9fa3-4b60-b2dd-b47739fa3148
ms.openlocfilehash: 14cd6fef80ff9ae3a9d78531785edab0da7cc6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73130909"
---
# <a name="applying-attributes"></a>Applicazione di attributi
Usare il processo seguente per applicare un attributo a un elemento del codice.  
  
1. Definire un nuovo attributo o usare un attributo esistente importando lo spazio dei nomi da .NET Framework.  
  
2. Applicare l'attributo dell'elemento di codice posizionandolo immediatamente prima dell'elemento.  
  
     Ogni linguaggio ha una propria sintassi di attributo. In C++ e C#, l'attributo è racchiuso tra parentesi quadre e separato dall'elemento da spazi vuoti, che possono includere un'interruzione di riga. In Visual Basic, l'attributo è racchiuso tra parentesi acute e deve essere nella stessa riga logica. Se si desidera un'interruzione di riga, è possibile usare il carattere di continuazione di riga.
  
3. Specificare i parametri posizionali e i parametri denominati per l'attributo.  
  
     I parametri posizionali sono necessari e devono precedere eventuali parametri denominati. Corrispondono ai parametri di uno dei costruttori dell'attributo. I parametri denominati sono facoltativi e corrispondono a proprietà dell'attributo di lettura/scrittura. In C++ e C# specificare `name`=`value` per ciascun parametro facoltativo, in cui `name` è il nome della proprietà. In Visual Basic specificare `name`:=`value`.  
  
 L'attributo viene emesso nei metadati quando si compila il codice ed è disponibile per il Common Language Runtime e qualsiasi strumento personalizzato o l'applicazione tramite i servizi di reflection di runtime.  
  
 Per convenzione, tutti i nomi dell'attributo terminano con Attribute. Tuttavia, per molti linguaggi destinati al runtime, come Visual Basic e C#, non è necessario specificare il nome completo di un attributo. Ad esempio, se si desidera inizializzare <xref:System.ObsoleteAttribute?displayProperty=nameWithType>, è necessario farvi riferimento come **Obsolete**.  
  
## <a name="applying-an-attribute-to-a-method"></a>Applicazione di un attributo a un metodo  
 L'esempio di codice seguente illustra come dichiarare **System.ObsoleteAttribute**, che marca il codice come obsoleto. La stringa `"Will be removed in next version"` viene passato all'attributo. Questo attributo genera un avviso del compilatore che mostra la stringa passata quando viene chiamato il codice descritto dall'attributo.  
  
 [!code-cpp[Conceptual.Attributes.Usage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#3)]
 [!code-csharp[Conceptual.Attributes.Usage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#3)]
 [!code-vb[Conceptual.Attributes.Usage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#3)]  
  
## <a name="applying-attributes-at-the-assembly-level"></a>Applicazione di attributi a livello di assembly  
 Se si desidera applicare un attributo a **assembly** livello`Assembly` di assembly, utilizzare la parola chiave assembly ( in Visual Basic). Nel codice riportato di seguito viene illustrato l'attributo **AssemblyTitleAttribute** applicato a livello di assembly.  
  
 [!code-cpp[Conceptual.Attributes.Usage#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#2)]
 [!code-csharp[Conceptual.Attributes.Usage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#2)]
 [!code-vb[Conceptual.Attributes.Usage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#2)]  
  
 Quando viene applicato questo attributo, la stringa `"My Assembly"` viene inserita nel manifesto dell'assembly nella porzione di metadati del file. È possibile visualizzare l'attributo tramite [Disassembler MSIL (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) o creando un programma personalizzato per recuperare l'attributo.  
  
## <a name="see-also"></a>Vedere anche

- [Attributi](../../../docs/standard/attributes/index.md)
- [Recupero di informazioni memorizzate negli attributi](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)
- [Concetti](/cpp/windows/attributed-programming-concepts)
- [Attributi (C#)](../../csharp/programming-guide/concepts/attributes/index.md)
- [Panoramica degli attributi (Visual Basic)](../../visual-basic/programming-guide/concepts/attributes/index.md)
