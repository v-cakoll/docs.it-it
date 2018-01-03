---
title: Option Strict Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "49"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a01edd918ea49c08defddb45bf23c33307e814f
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="option-strict-statement"></a>Option Strict Statement
Limita le conversioni implicite dei dati a conversioni di ampliamento solo, non consente l'associazione tardiva e la tipizzazione implicita che comporta un `Object` tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`On`|Facoltativo. Abilita `Option Strict` il controllo.|  
|`Off`|Facoltativo. Disabilita `Option Strict` il controllo.|  
  
## <a name="remarks"></a>Note  
 Quando `Option Strict On` o `Option Strict` viene visualizzato in un file, le condizioni seguenti generano un errore in fase di compilazione:  
  
-   Conversioni implicite verso un tipo di dati più piccolo  
  
-   Associazione tardiva  
  
-   Tipizzazione implicita che comporta un tipo `Object`  
  
> [!NOTE]
>  Nelle configurazioni di avviso che è possibile impostare per il [pagina Compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), sono disponibili tre impostazioni che corrispondono alle tre condizioni che causano un errore in fase di compilazione. Per informazioni su come usare queste impostazioni, vedere [per impostare le configurazioni di avviso nell'IDE](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) più avanti in questo argomento.  
  
 Il `Option Strict Off` istruzione consente di disattivare l'errore e avviso di controllo per tutte e tre le condizioni, anche se le impostazioni IDE associate specificano per attivare questi errori o avvisi. Il `Option Strict On` istruzione attiva errore e avviso di controllo per tutte e tre le condizioni, anche se specificano le impostazioni IDE associate per disattivare questi errori o avvisi.  
  
 Se utilizzato, il `Option Strict` istruzione deve precedere qualsiasi altra istruzione di codice in un file.  
  
 Quando si imposta `Option Strict` a `On`, Visual Basic controlla i tipi di dati sono specificati per tutti gli elementi di programmazione. Tipi di dati specificati in modo esplicito, o specificati utilizzando l'inferenza del tipo locale. Specifica di tipi di dati per tutti gli elementi di programmazione è consigliata, per i motivi seguenti:  
  
-   Consente il supporto IntelliSense per le variabili e parametri. In questo modo è possibile visualizzare le relative proprietà e gli altri membri durante la digitazione di codice.  
  
-   Consente al compilatore di eseguire il controllo dei tipi. Tipo di controllo consente di individuare le istruzioni che possono non riuscire in fase di esecuzione a causa di errori di conversione. Identifica, inoltre, le chiamate ai metodi su oggetti che non supportano tali metodi.  
  
-   Consente di velocizzare l'esecuzione del codice. Un motivo è che se non si specifica un tipo di dati per un elemento di programmazione, il compilatore Visual Basic assegna il `Object` tipo. Il codice compilato potrebbe essere necessario convertire avanti e indietro tra `Object` e altri tipi di dati, riducendo le prestazioni.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Errori di conversione di Narrowing implicite  
 Questi errori si verificano in presenza di una conversione implicita verso un tipo di dati più piccolo.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]convertire molti tipi di dati in altri tipi di dati. Quando il valore di un tipo di dati viene convertito in un tipo di dati con precisione inferiore o una capacità inferiore, possono verificarsi perdite di dati. Se tale conversione non riesce, si verifica un errore di run-time. `Option Strict`garantisce la notifica in fase di compilazione di queste conversioni verso un in modo che possano essere evitate. Per ulteriori informazioni, vedere [conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) e [conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Le conversioni che possono causare errori includono conversioni implicite che si verificano nelle espressioni. Per altre informazioni, vedere i seguenti argomenti:  
  
-   [Operatore +](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [Operatore +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ = (Operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Tipo di dati Char](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Quando si concatenano stringhe usando il [& operatore](../../../visual-basic/language-reference/operators/concatenation-operator.md), tutte le conversioni per le stringhe sono considerate di ampliamento. Affinché queste conversioni non generano un errore di conversione implicita verso, anche se `Option Strict` si trova in.  
  
 Quando si chiama un metodo che presenta un argomento che dispone di un tipo di dati diverso rispetto al parametro corrispondente, una conversione di narrowing causa un errore di compilazione se `Option Strict` si trova in. È possibile evitare l'errore in fase di compilazione tramite una conversione widening o una conversione esplicita.  
  
 Errori di conversione di narrowing implicite vengono soppressi in fase di compilazione per le conversioni dagli elementi in un `For Each…Next` insieme alla variabile di controllo del ciclo. Questo errore si verifica anche se `Option Strict` si trova in. Per ulteriori informazioni, vedere la sezione "Conversioni di restrizione" [For Each... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Errori di associazione tardiva  
 Un oggetto è ad associazione tardiva quando viene assegnato a una proprietà o a un metodo di una variabile dichiarata di tipo `Object`. Per ulteriori informazioni, vedere [anticipata e tardiva](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Errori di tipo di oggetto implicito  
 Si verificano errori di tipo di oggetto implicito quando non è possibile dedurre un tipo appropriato per una variabile dichiarata, pertanto viene dedotto il tipo `Object`. Questo errore si verifica principalmente quando si usa un'istruzione `Dim` per dichiarare una variabile senza usare una clausola `As` e `Option Infer` è Off. Per ulteriori informazioni, vedere [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) e [specifiche del linguaggio Visual Basic](../../../visual-basic/reference/language-specification/index.md).  
  
 Per i parametri di metodo, il `As` clausola è facoltativa se `Option Strict` è disattivata. Tuttavia, se un qualsiasi parametro utilizza un `As` clausola, essi deve essere utilizzata. Se `Option Strict` è abilitato, il `As` clausola è obbligatoria per ogni definizione di parametro.  
  
 Se si dichiara una variabile senza utilizzare un `As` clausola e impostarlo su `Nothing`, la variabile è di tipo `Object`. In questo caso verrà generato alcun errore in fase di compilazione quando `Option Strict` in e `Option Infer` si trova in. Un esempio di questo oggetto è `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Tipi di dati e valori predefiniti  
 Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e l'inizializzatore in un [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|Tipo di dati specificato?|Inizializzatore specificato?|Esempio|Risultato|  
|---|---|---|---|  
|No|No|`Dim qty`|Se `Option Strict` è disabilitato (impostazione predefinita), la variabile è impostata su `Nothing`.<br /><br /> Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|  
|No|Sì|`Dim qty = 5`|Se `Option Infer` è abilitato (impostazione predefinita), alla variabile viene assegnato il tipo di dati dell'inizializzatore. Vedere [inferenza](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.<br /><br /> Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|  
|Sì|No|`Dim qty As Integer`|La variabile viene inizializzata sul valore predefinito per il tipo di dati. Per ulteriori informazioni, vedere [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Yes|Sì|`Dim qty  As Integer = 5`|Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Quando non è presente un'istruzione Option Strict  
 Se il codice sorgente non contiene un `Option Strict` istruzione, il **Option strict** impostazione di [pagina Compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) viene utilizzato. Il **pagina Compila** dispone di impostazioni che consentono di controllare le condizioni che generano un errore.  
  
 Se si utilizza il compilatore della riga di comando, è possibile utilizzare il [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) per specificare un'impostazione per l'opzione del compilatore `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Per impostare Option Strict nell'IDE  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Nel **compilare** scheda, impostare il valore **Option Strict** casella.  
  
###  <a name="conditions"></a>Per impostare le configurazioni di avviso nell'IDE  
 Quando si utilizza il [pagina Compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) anziché un `Option Strict` istruzione, si ha un maggiore controllo sulle condizioni che generano errori. Il **configurazioni avvisi** sezione il **pagina Compila** ha impostazioni che corrispondono alle tre condizioni che causano un errore in fase di compilazione quando `Option Strict` si trova in. Queste impostazioni sono le seguenti:  
  
-   **Conversione implicita**  
  
-   **Binding tardivo. La chiamata potrebbe non riuscire in fase di esecuzione.**  
  
-   **Tipo implicito. Verrà utilizzato oggetto.**  
  
 Quando si imposta **Option Strict** su **On**, tutte e tre queste impostazioni di configurazione degli avvisi vengono impostate su **Errore**. Quando si imposta **Option Strict** su **Off**, tutte e tre le impostazioni vengono impostate su **Nessuno**.  
  
 È possibile modificare singolarmente ogni impostazione di configurazione degli avvisi su **Nessuno**, **Avviso** o **Errore**. Se tutte e tre le impostazioni di configurazione degli avvisi vengono impostate su **Errore**, nella casella `Option strict` viene visualizzato `On`. Se tutte e tre sono impostate su **Nessuno**, nella casella viene visualizzato `Off`. Per qualsiasi altra combinazione di queste impostazioni, viene visualizzato **(personalizzato)**.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Per impostare l'impostazione Option Strict per nuovi progetti  
 Quando si crea un progetto, il **Option Strict** impostazione di **compilare** scheda è impostata sul **Option Strict** impostazione nel **opzioni** la finestra di dialogo.  
  
 Per impostare `Option Strict` in questa finestra di dialogo nel **strumenti** menu, fare clic su **opzioni**. Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**. L'impostazione predefinita iniziale in **impostazioni predefinite di Visual Basic** è `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Per impostare Option Strict nella riga di comando  
 Includere il [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) opzione del compilatore nella **vbc** comando.  
  
## <a name="example"></a>Esempio  
 Gli esempi seguenti illustrano gli errori in fase di compilazione causati da conversioni implicite che sono conversioni di restrizione. Questa categoria di errori corrisponde alla **conversione implicita** condizione sul **pagina Compila**.  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un errore in fase di compilazione causato dall'associazione tardiva. Questa categoria di errori corrisponde alla **ritardo associazione; chiamata potrebbe non riuscire in fase di esecuzione** condizione sul **pagina Compila**.  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>Esempio  
 Gli esempi seguenti illustrano gli errori causati da variabili dichiarate con un tipo implicito di `Object`. Questa categoria di errori corrisponde alla **implicita del tipo; oggetto presuppone** condizione sul **pagina Compila**.  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Pagina Compilazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [Istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Procedura: accedere ai membri di un oggetto](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [Espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Associazione tardiva nelle soluzioni Office](https://msdn.microsoft.com/library/3xxe951d)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
