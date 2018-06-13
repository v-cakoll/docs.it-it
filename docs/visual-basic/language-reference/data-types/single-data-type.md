---
title: Tipo di dati Single (Visual Basic)
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
ms.openlocfilehash: 770961f225b139aaddf34b42327bca63638c725d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590782"
---
# <a name="single-data-type-visual-basic"></a>Tipo di dati Single (Visual Basic)
Contiene con segno a 32 bit IEEE (4 byte) e con precisione singola numeri a virgola mobile compresi nell'intervallo da - 3, 4028235E + 38 e-1, 401298E-45 per i valori negativi e tra 1, 401298E-45 a 3, 4028235E + 38 per i valori positivi. Numeri a precisione singola archiviano un'approssimazione di un numero reale.  
  
## <a name="remarks"></a>Note  
 Utilizzare il `Single` il tipo di dati per contenere i valori a virgola mobile che non richiedono l'ampiezza dei dati completo `Double`. In alcuni casi potrebbe essere in grado di pack common language runtime il `Single` variabili e ridurre il consumo di memoria.  
  
 Il valore predefinito di `Single` è 0.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Precisione.** Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre contengono una precisa rappresentazione in memoria. Ciò potrebbe provocare risultati imprevisti da alcune operazioni, ad esempio il confronto di valori e `Mod` operatore. Per ulteriori informazioni, vedere [risoluzione dei problemi dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Ampliamento.** Il `Single` può ampliarsi nel tipo di dati `Double`. È pertanto possibile convertire `Single` a `Double` senza che si verifichi un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
-   **Zeri finali.** I tipi di dati a virgola mobile non dispone di alcuna rappresentazione interna di caratteri 0 finali. Ad esempio, non distingue tra 4,2000 e 4.2. Di conseguenza, i caratteri 0 finali non vengono visualizzati quando si visualizzano o stampare i valori a virgola mobile.  
  
-   **Caratteri tipo.** Aggiungendo il carattere di tipo letterale `F` a un valore letterale, se ne determina la conversione nel tipo di dati `Single`. Aggiungendo il carattere identificatore di tipo `!` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Single`.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Single?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Single?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Tipo di dati Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
