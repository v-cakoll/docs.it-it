---
title: 'Procedura: determinare se un oggetto .NET Standard è serializzabile'
description: Viene illustrato come determinare se un tipo .NET Standard può essere serializzato in fase di esecuzione.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 247eed2e7091930c6bcfaa524296b45350dd6510
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580988"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Procedura: determinare se un oggetto .NET Standard è serializzabile

.NET Standard è una specifica che definisce i tipi e membri che devono essere presenti in implementazioni specifiche di .NET conformi a tale versione dello standard. Tuttavia, lo Standard di .NET non definisce se un tipo è serializzabile. I tipi definiti nella libreria Standard di .NET non contrassegnati con il <xref:System.SerializableAttribute> attributo. Invece, le implementazioni specifiche di .NET, ad esempio .NET Framework e .NET Core, sono disponibili per determinare se un determinato tipo è serializzabile. 

Se si sono creato una libreria che ha come destinazione .NET Standard, la libreria può essere utilizzata da qualsiasi implementazione di .NET che supporta lo Standard di .NET. Ciò significa che è possibile sapere in anticipo se un determinato tipo è serializzabile. è solo possibile determinare se è serializzabile in fase di esecuzione.

È possibile determinare se un oggetto serializzabile in fase di esecuzione eseguendo il recupero del valore del <xref:System.Type.IsSerializable> proprietà di un <xref:System.Type> oggetto che rappresenta il tipo dell'oggetto. Nell'esempio seguente fornisce un'implementazione. Definisce un `IsSerializable(Object)` metodo di estensione che indica se qualsiasi <xref:System.Object> istanza può essere serializzata.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

È quindi possibile passare qualsiasi oggetto al metodo per determinare se può essere serializzato e deserializzato nell'implementazione corrente di .NET, come illustrato nell'esempio seguente:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a>Vedere anche

[Serializzazione binaria](binary-serialization.md)   
<xref:System.SerializableAttribute?displayProperty=nameWithType>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
