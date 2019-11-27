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
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343924"
---
# <a name="single-data-type-visual-basic"></a>Tipo di dati Single (Visual Basic)

Include numeri a virgola mobile a precisione singola IEEE a 32 bit (4 byte) compresi tra-3.4028235 E + 38 e-401298E E-45 per i valori negativi e da 401298E E-45 a 3.4028235 E + 38 per i valori positivi. I numeri a precisione singola archiviano un'approssimazione di un numero reale.  
  
## <a name="remarks"></a>Note  

 Utilizzare il tipo di dati `Single` per contenere valori a virgola mobile che non richiedono la larghezza completa dei dati di `Double`. In alcuni casi è possibile che il Common Language Runtime sia in grado di comprimere le variabili di `Single` e di risparmiare sull'utilizzo della memoria.  
  
 Il valore predefinito di `Single` è 0.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
- **Precisione.** Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione precisa in memoria. Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l'operatore `Mod`. Per ulteriori informazioni, vedere [risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.  
  
- **Conversioni.** Il tipo di dati `Single` viene ampliato `Double`. Ciò significa che è possibile convertire `Single` in `Double` senza riscontrare un errore di <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Zeri finali.** I tipi di dati a virgola mobile non hanno alcuna rappresentazione interna di caratteri finali 0. Ad esempio, non si distinguono tra 4,2000 e 4,2. Di conseguenza, i caratteri finali 0 non vengono visualizzati quando si visualizzano o stampano valori a virgola mobile.  
  
- **Digitare i caratteri.** Aggiungendo il carattere di tipo letterale `F` a un valore letterale, se ne determina la conversione nel tipo di dati `Single`. Aggiungendo il carattere identificatore di tipo `!` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Single`.  
  
- **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Single?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Single?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Tipo di dati Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
