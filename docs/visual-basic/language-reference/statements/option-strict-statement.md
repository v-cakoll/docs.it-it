---
title: Istruzione Option Strict (Visual Basic)
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
ms.openlocfilehash: 1fce65b70c663ca56427122abb604d16fcd029d7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981543"
---
# <a name="option-strict-statement"></a>Option Strict Statement
Limita le conversioni di tipo di dati implicite per solo conversioni di ampliamento, non consente l'associazione tardiva e la tipizzazione implicita che comporta un `Object` tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`On`|Facoltativo. Abilita `Option Strict` controllo.|  
|`Off`|Facoltativo. Disabilita `Option Strict` controllo.|  
  
## <a name="remarks"></a>Note  
 Quando `Option Strict On` o `Option Strict` viene visualizzato in un file, le condizioni seguenti causano un errore in fase di compilazione:  
  
-   Conversioni implicite verso un tipo di dati più piccolo  
  
-   Associazione tardiva  
  
-   Tipizzazione implicita che comporta un tipo `Object`  
  
> [!NOTE]
>  Nelle configurazioni di avviso che è possibile impostare per il [pagina compilazione, creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), sono disponibili tre impostazioni che corrispondono alle tre condizioni che causano un errore in fase di compilazione. Per informazioni su come usare queste impostazioni, vedere [per impostare le configurazioni di avviso nell'IDE](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) più avanti in questo argomento.  
  
 Il `Option Strict Off` istruzione disattiva l'errore e avviso di controllo per tutte e tre le condizioni, anche se le impostazioni IDE associate specificano per attivare questi errori o avvisi. Il `Option Strict On` istruzione attiva errore e avviso di controllo per tutte e tre le condizioni, anche se le impostazioni IDE associate specificano per disattivare questi errori o avvisi.  
  
 Se usato, il `Option Strict` istruzione deve precedere qualsiasi altra istruzione di codice in un file.  
  
 Quando si imposta `Option Strict` a `On`, Visual Basic controlla i tipi di dati sono specificati per tutti gli elementi di programmazione. Tipi di dati possono essere specificati in modo esplicito o specificati tramite l'inferenza del tipo locale. Specifica dei tipi di dati per tutti gli elementi di programmazione è consigliata, per i motivi seguenti:  
  
-   Consente il supporto IntelliSense per le variabili e parametri. In questo modo è possibile visualizzare le relative proprietà e gli altri membri durante la digitazione di codice.  
  
-   Consente al compilatore di eseguire il controllo dei tipi. Controllo consente di che trovare le istruzioni che possono non riuscire in fase di esecuzione a causa di errori di conversione del tipo. Identifica anche le chiamate ai metodi su oggetti che non supportano tali metodi.  
  
-   Accelera l'esecuzione di codice. Uno dei motivi è che se non si specifica un tipo di dati per un elemento di programmazione, il compilatore Visual Basic assegna il `Object` tipo. Il codice compilato potrebbe essere necessario convertire spostarsi tra `Object` e altri tipi di dati, riducendo le prestazioni.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Errori di conversione di Narrowing implicite  
 Questi errori si verificano in presenza di una conversione implicita verso un tipo di dati più piccolo.  
  
 Visual Basic è possibile convertire altri tipi di dati di molti tipi di dati. Quando il valore di un tipo di dati viene convertito in un tipo di dati con precisione inferiore o con una capacità inferiore, può verificarsi una perdita di dati. Se tale conversione non riesce, si verifica un errore di run-time. `Option Strict` garantisce la notifica in fase di compilazione di queste conversioni di narrowing in modo che possano essere evitate. Per altre informazioni, vedere [conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) e [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Le conversioni che possono causare errori includono le conversioni implicite che si verificano nelle espressioni. Per altre informazioni, vedere i seguenti argomenti:  
  
-   [Operatore +](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [Operatore +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ = (Operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Tipo di dati Char](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Quando si concatenano le stringhe usando il [& operatore](../../../visual-basic/language-reference/operators/concatenation-operator.md), tutte le conversioni per le stringhe vengono considerate di ampliamento. In modo che queste conversioni non generano un errore di conversione narrowing implicite, anche se `Option Strict` si trova in.  
  
 Quando si chiama un metodo con un argomento che dispone di un tipo di dati diverso rispetto al parametro corrispondente, una conversione di narrowing provoca un errore in fase di compilazione se `Option Strict` si trova in. È possibile evitare l'errore in fase di compilazione tramite una conversione verso o una conversione esplicita.  
  
 Errori di conversione di narrowing implicite vengono soppressi in fase di compilazione per le conversioni dagli elementi in un `For Each…Next` insieme alla variabile di controllo del ciclo. Questo errore si verifica anche se `Option Strict` si trova in. Per altre informazioni, vedere la sezione "Conversioni di Narrowing" [For Each... Istruzione Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Errori di associazione tardiva  
 Un oggetto è ad associazione tardiva quando viene assegnato a una proprietà o a un metodo di una variabile dichiarata di tipo `Object`. Per altre informazioni, vedere [associazione anticipata e tardiva](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Errori di tipo di oggetto implicito  
 Si verificano errori di tipo di oggetto implicito quando non è possibile dedurre un tipo appropriato per una variabile dichiarata, pertanto viene dedotto il tipo `Object`. Questo errore si verifica principalmente quando si usa un'istruzione `Dim` per dichiarare una variabile senza usare una clausola `As` e `Option Infer` è Off. Per altre informazioni, vedere [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) e il [specifiche del linguaggio Visual Basic](../../../visual-basic/reference/language-specification/index.md).  
  
 Per i parametri di metodo, il `As` clausola è facoltativa se `Option Strict` è disattivata. Tuttavia, se un parametro viene utilizzato un `As` clausola, tutti devono usare lo. Se `Option Strict` è on, il `As` clausola è obbligatoria per ogni definizione di parametro.  
  
 Se si dichiara una variabile senza usare un `As` clausola e impostarla su `Nothing`, la variabile è di tipo `Object`. In questo caso verrà generato alcun errore in fase di compilazione quando `Option Strict` si trova in e `Option Infer` si trova in. Un esempio di ciò è `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Tipi di dati e valori predefiniti  
 Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e l'inizializzatore in un' [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|Tipo di dati specificato?|Inizializzatore specificato?|Esempio|Risultato|  
|---|---|---|---|  
|No|No|`Dim qty`|Se `Option Strict` è disabilitato (impostazione predefinita), la variabile è impostata su `Nothing`.<br /><br /> Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|  
|No|Sì|`Dim qty = 5`|Se `Option Infer` è abilitato (impostazione predefinita), alla variabile viene assegnato il tipo di dati dell'inizializzatore. Visualizzare [inferenza del tipo locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.<br /><br /> Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|  
|Sì|No|`Dim qty As Integer`|La variabile viene inizializzata sul valore predefinito per il tipo di dati. Per altre informazioni, vedere [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Sì|Sì|`Dim qty  As Integer = 5`|Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Quando non è presente un'istruzione Option Strict  
 Se il codice sorgente non contiene un `Option Strict` istruzione, il **Option strict** impostazione il [pagina compilazione, creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) viene usato. Il **pagina compilazione** dispone di impostazioni che consentono un maggiore controllo delle condizioni che generano un errore.  
  
 Se si usa il compilatore della riga di comando, è possibile usare la [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) opzione del compilatore per specificare un'impostazione per `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Per impostare Option Strict nell'IDE  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Nel **Compile** scheda, impostare il valore **Option Strict** casella.  
  
###  <a name="conditions"></a> Per impostare le configurazioni di avviso nell'IDE  
 Quando si usa la [pagina compilazione, creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) anziché un `Option Strict` istruzione, si ha un maggiore controllo delle condizioni che generano errori. Il **configurazioni avvisi** sezione il **pagina compilazione** dispone di impostazioni che corrispondono alle tre condizioni che causano un errore in fase di compilazione quando `Option Strict` si trova in. Queste impostazioni sono le seguenti:  
  
-   **Conversione implicita**  
  
-   **Binding tardivo. La chiamata potrebbe non riuscire in fase di esecuzione.**  
  
-   **Tipo implicito. Verrà utilizzato oggetto.**  
  
 Quando si imposta **Option Strict** su **On**, tutte e tre queste impostazioni di configurazione degli avvisi vengono impostate su **Errore**. Quando si imposta **Option Strict** su **Off**, tutte e tre le impostazioni vengono impostate su **Nessuno**.  
  
 È possibile modificare singolarmente ogni impostazione di configurazione degli avvisi su **Nessuno**, **Avviso** o **Errore**. Se tutte e tre le impostazioni di configurazione degli avvisi vengono impostate su **Errore**, nella casella `Option strict` viene visualizzato `On`. Se tutte e tre sono impostate su **Nessuno**, nella casella viene visualizzato `Off`. Per qualsiasi altra combinazione di queste impostazioni, viene visualizzato **(personalizzato)**.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Per impostare l'impostazione predefinita Option Strict per i nuovi progetti  
 Quando si crea un progetto, il **Option Strict** impostazione nel **compilare** scheda è impostata sul **Option Strict** impostazione nel **opzioni** finestra di dialogo.  
  
 Per impostare `Option Strict` nella finestra di dialogo, nel **Tools** menu, fare clic su **opzioni**. Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**. L'impostazione predefinita iniziale in **le impostazioni predefinite di Visual Basic** è `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Per impostare Option Strict nella riga di comando  
 Includere il [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) opzione del compilatore nella **vbc** comando.  
  
## <a name="example"></a>Esempio  
 Gli esempi seguenti illustrano gli errori in fase di compilazione causati da conversioni implicite che vengono delle conversioni narrowing. Questa categoria di errori corrisponde alla **conversione implicita** condizione il **pagina compilazione**.  
  
 [!code-vb[VbVbalrStatements#161](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#161)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente illustra un errore in fase di compilazione causato dall'associazione tardiva. Questa categoria di errori corrisponde alla **Late binding; chiamata potrebbe non riuscire in fase di esecuzione** condizione il **pagina compilazione**.  
  
 [!code-vb[VbVbalrStatements#162](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#162)]  
  
## <a name="example"></a>Esempio  
 Gli esempi seguenti illustrano gli errori causati da variabili dichiarate con un tipo implicito di `Object`. Questa categoria di errori corrisponde alla **tipo implicito: presunto oggetto** condizione il **pagina compilazione**.  
  
 [!code-vb[VbVbalrStatements#163](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#163)]  
  
 [!code-vb[VbVbalrStatements#164](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#164)]  
  
## <a name="see-also"></a>Vedere anche

- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Pagina Compilazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Procedura: Accedere ai membri di un oggetto](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [Espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Associazione tardiva nelle soluzioni Office](/visualstudio/vsto/late-binding-in-office-solutions)
- [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
