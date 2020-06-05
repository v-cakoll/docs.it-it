---
title: Istruzione Option Compare
ms.date: 07/20/2015
f1_keywords:
- vb.Compare
- vb.OptionCompare
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword [Visual Basic]
- binary comparison [Visual Basic]
- strings [Visual Basic], returning from functions
- binary comparison [Visual Basic], Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword [Visual Basic], Option Compare statement
- Binary keyword [Visual Basic], Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement [Visual Basic]
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
ms.openlocfilehash: 1ffe3e45a296d02364f488540d987d85133013bd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404382"
---
# <a name="option-compare-statement"></a>Istruzione Option Compare
Dichiara il metodo di confronto predefinito da usare durante il confronto dei dati di tipo stringa.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`Binary`|Facoltativa. Consente di eseguire confronti tra stringhe basati su un criterio di ordinamento derivato dalle rappresentazioni binarie interne dei caratteri.<br /><br /> Questo tipo di confronto è particolarmente utile se le stringhe possono contenere caratteri che non devono essere interpretati come testo. In questo caso, non è consigliabile consentire che il confronto sia falsato da equivalenze alfabetiche, ad esempio dalla mancata distinzione tra maiuscole e minuscole.|  
|`Text`|Facoltativa. Consente di eseguire confronti tra stringhe basati su un criterio di ordinamento testuale senza distinzione tra maiuscole e minuscole determinato dalle impostazioni locali del sistema.<br /><br /> Questo tipo di confronto è utile se le stringhe contengono tutti caratteri di testo e si vuole confrontarle prendendo in considerazione le equivalenze alfabetiche, quali la mancata distinzione tra maiuscole e minuscole e le lettere strettamente correlate. Ad esempio, è possibile considerare le lettere `A` e `a` equivalenti e fare in modo che le lettere `Ä` e `ä` precedano `B` e `b`.|  
  
## <a name="remarks"></a>Commenti  
 Se usato, è necessario includere l'istruzione `Option Compare` in un file prima di tutte le altre istruzioni del codice sorgente.  
  
 L'istruzione `Option Compare` specifica il metodo di confronto tra stringhe (`Binary` o `Text`).  Il metodo di confronto del testo predefinito è `Binary`.  
  
 Un confronto `Binary` confronta il valore numerico Unicode di ogni carattere in ciascuna stringa. Un confronto `Text` confronta ogni carattere Unicode in base al relativo significato lessicale nelle impostazioni cultura correnti.  
  
 Il criterio di ordinamento di Microsoft Windows è determinato dalla tabella codici. Per altre informazioni, vedere [Tabelle codici](/cpp/c-runtime-library/code-pages).  
  
 Nell'esempio seguente i caratteri nella tabella codici (ANSI 1252) per le lingue inglese ed europee vengono ordinati usando `Option Compare Binary`, che determina un tipico ordinamento binario.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Se gli stessi caratteri nella stessa tabella codici venissero ordinati con `Option Compare Text`, si otterrebbe il seguente ordinamento testuale.  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a>Quando non è presente un'istruzione Option Compare  
 Se il codice sorgente non contiene un' `Option Compare` istruzione, viene utilizzata l'impostazione **Option Compare** nella [pagina compilazione, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . Se si usa il compilatore da riga di comando, viene usata l'impostazione specificata dall'opzione del compilatore [-OptionCompare (](../../reference/command-line-compiler/optioncompare.md) .  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a>Per impostare Option Compare nell'IDE  
  
1. In **Esplora soluzioni**selezionare un progetto. Scegliere **Proprietà** dal menu **Progetto**.  
  
2. Fare clic sulla scheda **Compila**.  
  
3. Impostare il valore nella casella **Option Compare** .  
  
 Quando si crea un progetto, l'impostazione **Option Compare** nella scheda **Compila** viene impostata sull'impostazione **Option Compare** nella finestra di dialogo **Opzioni** . Per modificare questa impostazione, scegliere **Opzioni**dal menu **strumenti** . Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**. L'impostazione predefinita iniziale in impostazioni **predefinite di Visual Basic** è **Binary**.  
  
#### <a name="to-set-option-compare-on-the-command-line"></a>Per impostare Option Compare sulla riga di comando  
  
- Includere l'opzione del compilatore [-OptionCompare (](../../reference/command-line-compiler/optioncompare.md) nel comando **vbc** .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata l'istruzione `Option Compare` per impostare il confronto binario come metodo predefinito per il confronto tra stringhe. Per usare questo codice, rimuovere il commento dall'istruzione `Option Compare Binary` e inserirlo all'inizio del file di origine.  
  
 [!code-vb[VbVbalrStatements#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#45)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata l'istruzione `Option Compare` per impostare il criterio di ordinamento del testo senza distinzione tra maiuscole e minuscole come metodo predefinito per il confronto tra stringhe. Per usare questo codice, rimuovere il commento dall'istruzione `Option Compare Text` e inserirlo all'inizio del file di origine.  
  
 [!code-vb[VbVbalrStatements#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#46)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>
- <xref:Microsoft.VisualBasic.Strings.Replace%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [-optioncompare](../../reference/command-line-compiler/optioncompare.md)
- [Operatori di confronto](../operators/comparison-operators.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatore Like](../operators/like-operator.md)
- [Funzioni stringa](../functions/string-functions.md)
- [Istruzione Option Explicit](option-explicit-statement.md)
- [Option Strict Statement](option-strict-statement.md)
