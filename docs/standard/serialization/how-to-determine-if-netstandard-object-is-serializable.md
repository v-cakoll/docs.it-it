---
title: Come determinare se un oggetto .NET Standard è serializzabile
description: Viene illustrato come determinare se un tipo di .NET Standard può essere serializzato in fase di esecuzione.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 4037dee36aeb619eb2757016904fd877158e57cf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159897"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Come determinare se un oggetto .NET Standard è serializzabile

Il .NET Standard è una specifica che definisce i tipi e i membri che devono essere presenti in implementazioni .NET specifiche conformi a tale versione dello standard. Tuttavia, il .NET Standard non definisce se un tipo è serializzabile. I tipi definiti nella libreria .NET Standard non sono contrassegnati con l'attributo <xref:System.SerializableAttribute>. Al contrario, le implementazioni di .NET specifiche, ad esempio .NET Framework e .NET Core, sono gratuite per determinare se un determinato tipo è serializzabile.

Se è stata sviluppata una libreria destinata al .NET Standard, la libreria può essere utilizzata da qualsiasi implementazione di .NET che supporti l'.NET Standard. Ciò significa che non è possibile sapere in anticipo se un determinato tipo è serializzabile; è possibile determinare solo se è serializzabile in fase di esecuzione.

È possibile determinare se un oggetto è serializzabile in fase di esecuzione recuperando il valore della proprietà <xref:System.Type.IsSerializable> di un oggetto <xref:System.Type> che rappresenta il tipo di tale oggetto. Nell'esempio seguente viene fornita un'implementazione di. Definisce un metodo di estensione `IsSerializable(Object)` che indica se è possibile serializzare un'istanza di <xref:System.Object>.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

È quindi possibile passare qualsiasi oggetto al metodo per determinare se può essere serializzato e deserializzato nell'implementazione .NET corrente, come illustrato nell'esempio seguente:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Serializzazione binaria](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
