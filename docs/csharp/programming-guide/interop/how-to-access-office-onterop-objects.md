---
title: Come accedere a oggetti di interoperabilità di Office- C# Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- optional parameters [C#], Office programming
- named and optional arguments [C#], Office programming
- dynamic [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
- Office programming [C#]
ms.assetid: 041b25c2-3512-4e0f-a4ea-ceb2999e4d5e
ms.openlocfilehash: b5d2da011ec6318c8b07f1eb4d383a4d56488239
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75700835"
---
# <a name="how-to-access-office-interop-objects-c-programming-guide"></a>Come accedere agli oggetti di interoperabilità di Office (C# guida per programmatori)

C#dispone di funzionalità che semplificano l'accesso agli oggetti API di Office. Le nuove funzionalità includono argomenti denominati e facoltativi, un nuovo tipo chiamato `dynamic` e la possibilità di passare argomenti a parametri di riferimento nei metodi COM come se fossero parametri di valore.

In questo argomento si useranno le nuove funzionalità per scrivere codice che consente di creare e visualizzare un foglio di lavoro di Microsoft Office Excel. Quindi si scriverà il codice per aggiungere un documento di Office Word contenente un'icona che è collegata al foglio di lavoro di Excel.

Per completare questa procedura dettagliata, è necessario aver installato nel computer Microsoft Office Excel 2007 e Microsoft Office Word 2007 o versioni successive.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a>Per creare un nuovo progetto di applicazione console

1. Avviare Visual Studio.

2. Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**. Verrà visualizzata la finestra di dialogo **Nuovo progetto**.

3. Nel riquadro **Modelli installati** espandere **Visual C#** e fare clic su **Windows**.

4. Nella parte superiore della finestra di dialogo **Nuovo progetto** assicurarsi che **.NET Framework 4**, o versione successiva, sia selezionato come framework di destinazione.

5. Nel riquadro **Modelli** fare clic su **Applicazione console**.

6. Digitare un nome per il progetto nel campo **Nome**.

7. Fare clic su **OK**.

     Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.

## <a name="to-add-references"></a>Per aggiungere riferimenti

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nome del progetto e quindi scegliere **Aggiungi riferimento**. Viene visualizzata la finestra di dialogo **Aggiungi riferimento**.

2. Nella pagina **Assembly** selezionare **Microsoft.Office.Interop.Word** nell'elenco **Nome componente** e, tenendo premuto CTRL, selezionare **Microsoft.Office.Interop.Excel**.  Se gli assembly non sono visibili, potrebbe essere necessario assicurarsi che siano installati e visualizzati. Vedere [procedura: installare gli assembly di interoperabilità primari di Office](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies).

3. Fare clic su **OK**.

## <a name="to-add-necessary-using-directives"></a>Per aggiungere le direttive using necessarie

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *Program.cs* e quindi fare clic su **Visualizza codice**.

2. Aggiungere le seguenti direttive di `using` all'inizio del file di codice:

     [!code-csharp[csProgGuideOfficeHowTo#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#1)]

## <a name="to-create-a-list-of-bank-accounts"></a>Per creare un elenco di conti correnti bancari

1. Incollare la seguente definizione di classe in **Program.cs**, sotto la classe `Program`.

     [!code-csharp[csProgGuideOfficeHowTo#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#2)]

2. Aggiungere il seguente codice al metodo `Main` per creare un elenco `bankAccounts` contenente due conti.

     [!code-csharp[csProgGuideOfficeHowTo#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#3)]

## <a name="to-declare-a-method-that-exports-account-information-to-excel"></a>Per dichiarare un metodo che consente di esportare informazioni sul conto in Excel

1. Aggiungere il seguente metodo alla classe `Program` per impostare un foglio di lavoro di Excel.

     Il metodo <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> usa un parametro facoltativo per specificare un modello particolare. I parametri facoltativi, una novità di C# 4, consentono di omettere l'argomento per il parametro se si vuole usare il valore predefinito del parametro. Poiché nessun argomento viene inviato nel codice seguente, `Add` usa il modello predefinito e crea una nuova cartella di lavoro. L'istruzione equivalente nelle precedenti versioni di C# richiede un argomento segnaposto: `ExcelApp.Workbooks.Add(Type.Missing)`.

     [!code-csharp[csProgGuideOfficeHowTo#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#4)]

2. Aggiungere il codice seguente alla fine di `DisplayInExcel`. Il codice consente di inserire valori nelle prime due colonne della prima riga del foglio di lavoro.

     [!code-csharp[csProgGuideOfficeHowTo#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#5)]

3. Aggiungere il codice seguente alla fine di `DisplayInExcel`. Il ciclo `foreach` inserisce le informazioni dall'elenco dei conti nelle prime due colonne delle righe successive del foglio di lavoro.

     [!code-csharp[csProgGuideOfficeHowTo#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#7)]

4. Aggiungere il seguente codice alla fine di `DisplayInExcel` per regolare la larghezza delle colonne in modo da adattarle al contenuto.

     [!code-csharp[csProgGuideOfficeHowTo#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#13)]

     Nelle versioni precedenti di C# è necessario eseguire il cast in modo esplicito per queste operazioni perché `ExcelApp.Columns[1]` restituisce `Object`, e `AutoFit` è un metodo <xref:Microsoft.Office.Interop.Excel.Range> di Excel. Le righe seguenti indicano il cast.

     [!code-csharp[csProgGuideOfficeHowTo#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#14)]

     C#4 e versioni successive, converte automaticamente il `Object` restituito in `dynamic` se all'assembly viene fatto riferimento dall'opzione del compilatore [-link](../../language-reference/compiler-options/link-compiler-option.md) o, in modo analogo, se la proprietà **Incorpora tipi di interoperabilità** di Excel è impostata su true. True è il valore predefinito di questa proprietà.

## <a name="to-run-the-project"></a>Per eseguire il progetto

1. Aggiungere la riga seguente alla fine di `Main`.

     [!code-csharp[csProgGuideOfficeHowTo#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#8)]

2. Premere CTRL+F5.

     Viene visualizzato un foglio di lavoro di Excel che contiene i dati dei due conti.

## <a name="to-add-a-word-document"></a>Per aggiungere un documento di Word

1. Per illustrare altri modi in cui C# 4 e versioni successive consentono di migliorare la programmazione di Office, il codice seguente apre un'applicazione Word e crea un'icona di collegamento al foglio di lavoro di Excel.

     Incollare il metodo `CreateIconInWordDoc`, fornito più avanti in questo passaggio, nella classe `Program`. `CreateIconInWordDoc` usa argomenti denominati e facoltativi per ridurre la complessità delle chiamate ai metodi di <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> e <xref:Microsoft.Office.Interop.Word.Selection.PasteSpecial%2A>. Queste chiamate incorporano altre due nuove funzionalità introdotte in C# 4 che semplificano le chiamate ai metodi COM con parametri di riferimento. In primo luogo, è possibile inviare argomenti ai parametri di riferimento come se fossero parametri di valore. In altre parole, è possibile inviare i valori direttamente, senza creare una variabile per ogni parametro referenziato. Il compilatore genera variabili temporanee per conservare i valori degli argomenti ed elimina le variabili restituite dalla chiamata. In secondo luogo, è possibile omettere la parola chiave `ref` nell'elenco di argomenti.

     Il metodo `Add` ha quattro parametri di riferimento, tutti facoltativi. In C# 4.0 e versioni successive è possibile omettere gli argomenti per alcuni o tutti i parametri se si vogliono usare i valori predefiniti. In C# 3.0 e versioni precedenti, è necessario fornire un argomento per ogni parametro e l'argomento deve essere una variabile perché i parametri sono di riferimento.

     Il metodo `PasteSpecial` inserisce il contenuto degli Appunti. Il metodo ha sette parametri di riferimento, tutti facoltativi. Il codice seguente consente di specificare gli argomenti per due di essi: `Link`, per creare un collegamento all'origine del contenuto degli Appunti e `DisplayAsIcon`, per visualizzare il collegamento come icona. In C# 4.0 e versioni successive è possibile usare argomenti denominati per questi due parametri e omettere gli altri. Anche se si tratta di parametri di riferimento, non è necessario usare la parola chiave `ref` o creare variabili per inviarle come argomenti. È possibile inviare direttamente i valori. In C# 3.0 e versioni precedenti, è necessario specificare un argomento variabile per ogni parametro di riferimento.

     [!code-csharp[csProgGuideOfficeHowTo#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#9)]

     In C# 3.0 e versioni precedenti del linguaggio, è necessario il codice più complesso seguente.

     [!code-csharp[csProgGuideOfficeHowTo#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#10)]

2. Aggiungere la seguente istruzione dopo `Main`.

     [!code-csharp[csProgGuideOfficeHowTo#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#11)]

3. Aggiungere la seguente istruzione dopo `DisplayInExcel`. Il metodo `Copy` aggiunge il foglio di lavoro negli Appunti.

     [!code-csharp[csProgGuideOfficeHowTo#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#12)]

4. Premere CTRL+F5.

     Verrà visualizzato un documento di Word contenente un'icona. Fare doppio clic sull'icona per visualizzare il foglio di lavoro in primo piano.

## <a name="to-set-the-embed-interop-types-property"></a>Per impostare la proprietà Incorpora tipi di interoperabilità

1. Quando si chiama un tipo COM che non richiede un assembly di interoperabilità primario (PIA) in fase di esecuzione, sono possibili altri miglioramenti. Eliminando la dipendenza dai risultati dei PIA produce l'indipendenza dalla versione e semplifica la distribuzione. Per altre informazioni sui vantaggi della programmazione senza PIA, vedere [Procedura dettagliata: incorporamento di tipi da assembly gestiti](../../../standard/assembly/embed-types-visual-studio.md).

     Inoltre, la programmazione è più semplice perché i tipi richiesti e restituiti dai metodi COM possono essere rappresentati usando il tipo `dynamic` anziché `Object`. Le variabili di tipo `dynamic` non saranno valutate fino al runtime, eliminando la necessità del cast esplicito. Per altre informazioni, vedere [Uso del tipo dynamic](../types/using-type-dynamic.md).

     In C# 4 il comportamento predefinito consiste nell'incorporare le informazioni di tipo invece di usare i PIA. A causa di tale impostazione predefinita, molti degli esempi precedenti vengono semplificati perché non è necessario eseguire il cast esplicito. Ad esempio, la dichiarazione di `worksheet` in `DisplayInExcel` è scritta come `Excel._Worksheet workSheet = excelApp.ActiveSheet` piuttosto che `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`. Anche le chiamate a `AutoFit` nello stesso metodo richiederebbero il cast esplicito senza valore predefinito, perché `ExcelApp.Columns[1]` restituisce un `Object` e `AutoFit` è un metodo Excel. Nel codice seguente viene illustrato il cast.

     [!code-csharp[csProgGuideOfficeHowTo#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#14)]

2. Per modificare l'impostazione predefinita e usare i PIA anziché incorporare le informazioni sul tipo, espandere il nodo **Riferimenti** in **Esplora soluzioni** e selezionare **Microsoft.Office.Interop.Excel** o **Microsoft.Office.Interop.Word**.

3. Se non è possibile visualizzare la finestra **Proprietà**, premere **F4**.

4. Trovare **Incorpora tipi di interoperabilità** nell'elenco delle proprietà e modificarne il valore in **False**. In modo analogo, è possibile compilare usando l'opzione del compilatore [-Reference](../../language-reference/compiler-options/reference-compiler-option.md) invece di [-link](../../language-reference/compiler-options/link-compiler-option.md) al prompt dei comandi.

## <a name="to-add-additional-formatting-to-the-table"></a>Per aggiungere ulteriore formattazione alla tabella

1. Sostituire le due chiamate a `AutoFit` in `DisplayInExcel` con la seguente istruzione.

     [!code-csharp[csProgGuideOfficeHowTo#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#15)]

     Il metodo <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> ha sette parametri di valore facoltativi. Gli argomenti denominati e facoltativi consentono di specificare gli argomenti per nessuno, alcuni o tutti i parametri. Nell'istruzione precedente, viene fornito un argomento per uno solo dei parametri, `Format`. Poiché `Format` è il primo parametro nell'elenco, non è necessario fornire il nome del parametro. Tuttavia, l'istruzione potrebbe essere più facile da comprendere se si include il nome del parametro, come illustrato nel codice seguente.

     [!code-csharp[csProgGuideOfficeHowTo#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#16)]

2. Premere CTRL + F5 per visualizzare il risultato. Altri formati sono elencati nell'enumerazione <xref:Microsoft.Office.Interop.Excel.XlRangeAutoFormat>.

3. Confrontare l'istruzione nel passaggio 1 con il codice seguente, che illustra gli argomenti necessari in C# 3.0 e versioni precedenti.

     [!code-csharp[csProgGuideOfficeHowTo#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#17)]

## <a name="example"></a>Esempio

Nel codice seguente viene illustrato l'esempio completo.

[!code-csharp[csProgGuideOfficeHowTo#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/walkthrough.cs#18)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Type.Missing?displayProperty=nameWithType>
- [dynamic](../../language-reference/builtin-types/reference-types.md)
- [Uso del tipo dinamico](../types/using-type-dynamic.md)
- [Argomenti denominati e facoltativi](../classes-and-structs/named-and-optional-arguments.md)
- [Come usare gli argomenti denominati e facoltativi nella programmazione di Office](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
