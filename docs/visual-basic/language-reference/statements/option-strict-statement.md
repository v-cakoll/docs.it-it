---
title: Option Strict Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Strict
- vb.OptionStrict
helpviewer_keywords:
- Strict keyword [Visual Basic]
- Option Strict statement [Visual Basic]
- conversions [Visual Basic], implicit
- late binding [Visual Basic]
- implicit conversions [Visual Basic]
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
ms.openlocfilehash: 9c86ae6be86591445dde3cc4e7bdd38aa4a7f0fa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404343"
---
# <a name="option-strict-statement"></a>Option Strict Statement
Limita le conversioni implicite dei tipi di dati solo per le conversioni verso un tipo di dati più ampio, non consente l'associazione tardiva e impedisce la tipizzazione implicita che restituisce un `Object` tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`On`|Facoltativa. Consente `Option Strict` il controllo.|  
|`Off`|Facoltativa. Disabilita `Option Strict` il controllo.|  
  
## <a name="remarks"></a>Commenti  
 Quando `Option Strict On` o `Option Strict` viene visualizzato in un file, le condizioni seguenti generano un errore in fase di compilazione:  
  
- Conversioni implicite verso un tipo di dati più piccolo  
  
- Associazione tardiva  
  
- Tipizzazione implicita che comporta un tipo `Object`  
  
> [!NOTE]
> Nelle configurazioni di avviso che è possibile impostare nella [pagina compilazione, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), sono disponibili tre impostazioni che corrispondono alle tre condizioni che provocano un errore in fase di compilazione. Per informazioni sull'utilizzo di queste impostazioni, vedere [per impostare le configurazioni di avviso nell'IDE](option-strict-statement.md#conditions) più avanti in questo argomento.  
  
 L' `Option Strict Off` istruzione disattiva il controllo degli errori e degli avvisi per tutte e tre le condizioni, anche se le impostazioni IDE associate specificano di attivare questi errori o avvisi. L' `Option Strict On` istruzione attiva il controllo di errori e avvisi per tutte e tre le condizioni, anche se le impostazioni IDE associate specificano di disattivare questi errori o avvisi.  
  
 Se utilizzata, l' `Option Strict` istruzione deve essere visualizzata prima di qualsiasi altra istruzione di codice in un file.  
  
 Quando si imposta `Option Strict` su `On` , Visual Basic verifica che i tipi di dati siano specificati per tutti gli elementi di programmazione. I tipi di dati possono essere specificati in modo esplicito o specificati tramite l'inferenza del tipo locale. È consigliabile specificare i tipi di dati per tutti gli elementi di programmazione, per i motivi seguenti:  
  
- Abilita il supporto IntelliSense per le variabili e i parametri. Questo consente di visualizzare le relative proprietà e altri membri durante la digitazione del codice.  
  
- Consente al compilatore di eseguire il controllo dei tipi. Il controllo dei tipi consente di trovare istruzioni che possono avere esito negativo in fase di esecuzione a causa di errori di conversione del tipo. Identifica inoltre le chiamate ai metodi su oggetti che non supportano tali metodi.  
  
- Accelera l'esecuzione del codice. Un motivo è che se non si specifica un tipo di dati per un elemento di programmazione, il compilatore Visual Basic lo assegna al `Object` tipo. Il codice compilato potrebbe dover eseguire la conversione tra `Object` e altri tipi di dati, riducendo così le prestazioni.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Errori di conversione implicita verso un tipo di restringimento  
 Questi errori si verificano in presenza di una conversione implicita verso un tipo di dati più piccolo.  
  
 Visual Basic possibile convertire molti tipi di dati in altri tipi di dati. È possibile che si verifichi una perdita di dati quando il valore di un tipo di dati viene convertito in un tipo di dati con una precisione minore o con una capacità minore. Si verifica un errore di run-time se tale conversione non riesce. `Option Strict`garantisce la notifica in fase di compilazione di queste conversioni verso un tipo di caratteri più piccolo, in modo che sia possibile evitarle. Per altre informazioni, vedere [conversioni implicite ed esplicite](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) e conversioni verso un tipo di dati più piccolo e più [ampio](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Le conversioni che possono causare errori includono conversioni implicite che si verificano nelle espressioni. Per altre informazioni, vedere gli argomenti seguenti:  
  
- [Operatore +](../operators/addition-operator.md)  
  
- [Operatore + =](../operators/addition-assignment-operator.md)  
  
- [Operatore \ (Visual Basic)](../operators/integer-division-operator.md)  
  
- [Operatore /= (Visual Basic)](../operators/floating-point-division-assignment-operator.md)  
  
- [Tipo di dati Char](../data-types/char-data-type.md)  
  
 Quando si concatenano stringhe usando l' [operatore&](../operators/concatenation-operator.md), tutte le conversioni alle stringhe vengono considerate più estese. Pertanto, queste conversioni non generano un errore di conversione implicita verso un tipo di caratteri più piccolo, anche se `Option Strict` è on.  
  
 Quando si chiama un metodo con un argomento con un tipo di dati diverso dal parametro corrispondente, una conversione verso un tipo di dati più piccolo causa un errore in fase di compilazione se `Option Strict` è on. È possibile evitare l'errore in fase di compilazione utilizzando una conversione verso un tipo di oggetto più ampio o una conversione esplicita.  
  
 Gli errori di conversione implicita verso un tipo di caratteri più piccolo vengono eliminati in fase di compilazione per le conversioni dagli elementi di una `For Each…Next` raccolta alla variabile di controllo del ciclo. Ciò si verifica anche se `Option Strict` è on. Per ulteriori informazioni, vedere la sezione relativa alle conversioni verso un tipo di dati più piccolo in [per ciascuna... Istruzione successiva](for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Errori di associazione tardiva  
 Un oggetto è ad associazione tardiva quando viene assegnato a una proprietà o a un metodo di una variabile dichiarata di tipo `Object`. Per ulteriori informazioni, vedere [associazione anticipata e tardiva](../../programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Errori di tipo di oggetto implicito  
 Si verificano errori di tipo di oggetto implicito quando non è possibile dedurre un tipo appropriato per una variabile dichiarata, pertanto viene dedotto il tipo `Object`. Questo errore si verifica principalmente quando si usa un'istruzione `Dim` per dichiarare una variabile senza usare una clausola `As` e `Option Infer` è Off. Per ulteriori informazioni, vedere l' [istruzione Option deduce](option-infer-statement.md) e la [specifica del linguaggio Visual Basic](../../reference/language-specification/index.md).  
  
 Per i parametri del metodo, la `As` clausola è facoltativa se `Option Strict` è disattivata. Tuttavia, se uno dei parametri usa una `As` clausola, è necessario che tutti lo usino. Se `Option Strict` è on, la `As` clausola è obbligatoria per ogni definizione di parametro.  
  
 Se si dichiara una variabile senza usare una `As` clausola e la si imposta su `Nothing` , la variabile ha un tipo di `Object` . In questo caso non si verifica alcun errore in fase di compilazione quando `Option Strict` è on e `Option Infer` è on. Un esempio è `Dim something = Nothing` .  
  
### <a name="default-data-types-and-values"></a>Tipi di dati e valori predefiniti  
 Nella tabella seguente vengono descritti i risultati di diverse combinazioni di specifica del tipo di dati e dell'inizializzatore in un' [istruzione Dim](dim-statement.md).  
  
|Tipo di dati specificato?|Inizializzatore specificato?|Esempio|Risultato|  
|---|---|---|---|  
|No|No|`Dim qty`|Se `Option Strict` è disabilitato (impostazione predefinita), la variabile è impostata su `Nothing`.<br /><br /> Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|  
|No|Sì|`Dim qty = 5`|Se `Option Infer` è abilitato (impostazione predefinita), alla variabile viene assegnato il tipo di dati dell'inizializzatore. Vedere [inferenza del tipo locale](../../programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.<br /><br /> Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|  
|Sì|No|`Dim qty As Integer`|La variabile viene inizializzata sul valore predefinito per il tipo di dati. Per ulteriori informazioni, vedere [istruzione Dim](dim-statement.md).|  
|Sì|Sì|`Dim qty  As Integer = 5`|Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Quando non è presente un'istruzione Option Strict  
 Se il codice sorgente non contiene un' `Option Strict` istruzione, viene utilizzata l'impostazione **Option Strict** nella [pagina compilazione, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . Nella **pagina Compila** sono disponibili impostazioni che consentono di controllare ulteriormente le condizioni che generano un errore.  
  
 Se si usa il compilatore da riga di comando, è possibile usare l'opzione del compilatore [-OptionStrict (](../../reference/command-line-compiler/optionstrict.md) per specificare un'impostazione per `Option Strict` .  
  
### <a name="to-set-option-strict-in-the-ide"></a>Per impostare Option Strict nell'IDE  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1. In **Esplora soluzioni**selezionare un progetto. Scegliere **Proprietà** dal menu **Progetto**.  
  
2. Nella scheda **Compila** , impostare il valore nella casella **Option Strict** .  
  
### <a name="to-set-warning-configurations-in-the-ide"></a><a name="conditions"></a>Per impostare le configurazioni di avviso nell'IDE  
 Quando si usa la [pagina Compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) invece di un' `Option Strict` istruzione, è possibile controllare ulteriormente le condizioni che generano errori. Nella sezione delle **configurazioni di avviso** della **pagina Compila** sono presenti impostazioni che corrispondono alle tre condizioni che generano un errore in fase di compilazione quando `Option Strict` è on. Queste impostazioni sono le seguenti:  
  
- **Conversione implicita**  
  
- **Binding tardivo. La chiamata potrebbe non riuscire in fase di esecuzione.**  
  
- **Tipo implicito. Verrà utilizzato oggetto.**  
  
 Quando si imposta **Option Strict** su **On**, tutte e tre queste impostazioni di configurazione degli avvisi vengono impostate su **Errore**. Quando si imposta **Option Strict** su **Off**, tutte e tre le impostazioni vengono impostate su **Nessuno**.  
  
 È possibile modificare singolarmente ogni impostazione di configurazione degli avvisi su **Nessuno**, **Avviso** o **Errore**. Se tutte e tre le impostazioni di configurazione degli avvisi sono impostate su **errore**, `On` viene visualizzato nella `Option strict` casella. Se tutti e tre sono impostati su **None**, `Off` viene visualizzato in questa casella. Per qualsiasi altra combinazione di queste impostazioni, viene visualizzato **(personalizzato)**.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Per impostare l'impostazione predefinita Option Strict per i nuovi progetti  
 Quando si crea un progetto, l'impostazione **Option Strict** nella scheda **Compila** viene impostata sull'impostazione **Option Strict** nella finestra di dialogo **Opzioni** .  
  
 Per impostare `Option Strict` in questa finestra di dialogo, scegliere **Opzioni**dal menu **strumenti** . Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**. L'impostazione predefinita iniziale in impostazioni **predefinite di Visual Basic** è `Off` .  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Per impostare Option Strict nella riga di comando  
 Includere l'opzione del compilatore [-OptionStrict (](../../reference/command-line-compiler/optionstrict.md) nel comando **vbc** .  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti vengono illustrati gli errori in fase di compilazione causati da conversioni di tipi implicite che sono conversioni verso un tipo di testo più piccolo. Questa categoria di errori corrisponde alla condizione di **conversione implicita** nella **pagina Compila**.  
  
 [!code-vb[VbVbalrStatements#161](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#161)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un errore in fase di compilazione causato dall'associazione tardiva. Questa categoria di errori corrisponde all' **associazione tardiva; la chiamata potrebbe non riuscire in fase di esecuzione** nella **pagina Compila**.  
  
 [!code-vb[VbVbalrStatements#162](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#162)]  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti vengono illustrati gli errori causati da variabili dichiarate con un tipo implicito di `Object` . Questa categoria di errori corrisponde al **tipo implicito** . la condizione presuppone l'oggetto nella **pagina di compilazione**.  
  
 [!code-vb[VbVbalrStatements#163](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#163)]  
  
 [!code-vb[VbVbalrStatements#164](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#164)]  
  
## <a name="see-also"></a>Vedere anche

- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversioni implicite ed esplicite](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Compilazione (pagina), Creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Istruzione Option Explicit](option-explicit-statement.md)
- [CString](../functions/type-conversion-functions.md)
- [Procedura: accedere ai membri di un oggetto](../../programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [Espressioni incorporate in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Conversione di tipo relaxed del delegato](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Late Binding in Office Solutions](/visualstudio/vsto/late-binding-in-office-solutions)
- [-optionstrict](../../reference/command-line-compiler/optionstrict.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
