---
title: Tipo di dati Single
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: ecb0f5f6416a2dd4ddd6888cb80ed3ac11ee58df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415531"
---
# <a name="single-data-type-visual-basic"></a>Tipo di dati Single (Visual Basic)

Include numeri a virgola mobile a precisione singola IEEE a 32 bit (4 byte) compresi tra-3.4028235 E + 38 e-401298E E-45 per i valori negativi e da 401298E E-45 a 3.4028235 E + 38 per i valori positivi. I numeri a precisione singola archiviano un'approssimazione di un numero reale.  
  
## <a name="remarks"></a>Commenti  

 Utilizzare il `Single` tipo di dati per contenere valori a virgola mobile che non richiedono la larghezza dei dati completa di `Double` . In alcuni casi è possibile che il Common Language Runtime sia in grado di comprimere le variabili in modo `Single` stretto e di risparmiare sull'utilizzo della memoria.  
  
 Il valore predefinito di `Single` è 0.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
- **Precisione.** Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione precisa in memoria. Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l' `Mod` operatore. Per ulteriori informazioni, vedere [risoluzione dei problemi](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.  
  
- **Conversioni.** Il `Single` tipo di dati viene ampliato a `Double` . Ciò significa che è possibile `Single` eseguire la conversione in `Double` senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
- **Zeri finali.** I tipi di dati a virgola mobile non hanno alcuna rappresentazione interna di caratteri finali 0. Ad esempio, non si distinguono tra 4,2000 e 4,2. Di conseguenza, i caratteri finali 0 non vengono visualizzati quando si visualizzano o stampano valori a virgola mobile.  
  
- **Digitare i caratteri.** Aggiungendo il carattere di tipo letterale `F` a un valore letterale, se ne determina la conversione nel tipo di dati `Single`. Aggiungendo il carattere identificatore di tipo `!` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Single`.  
  
- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Single?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Single?displayProperty=nameWithType>
- [Tipi di dati](index.md)
- [Tipo di dati Decimal](decimal-data-type.md)
- [Tipo di dati Double](double-data-type.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
