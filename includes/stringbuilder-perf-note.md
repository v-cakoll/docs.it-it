L'uso dell'indicizzazione basata sui caratteri con la proprietà <xref:System.Text.StringBuilder.Chars%2A> può essere lentissimo nelle condizioni seguenti:

- L'istanza <xref:System.Text.StringBuilder> è di grandi dimensioni (ad esempio, è costituita da diverse decine di migliaia di caratteri).
- <xref:System.Text.StringBuilder> è "pesante". Ovvero, le chiamate ripetute ai metodi, ad esempio <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>, hanno automaticamente espanso la proprietà <xref:System.Text.StringBuilder.Capacity%2A?displayProperty=nameWithType> dell'oggetto e allocato nuovi blocchi di memoria alla stessa.

L'impatto sulle prestazioni è notevole poiché ogni accesso ai caratteri scorre l'intero elenco di blocchi collegato per trovare il buffer corretto in cui eseguire l'indicizzazione.

> [!NOTE]
>  Nel caso di un oggetto <xref:System.Text.StringBuilder> "pesante" e di grandi dimensioni, usare la proprietà <xref:System.Text.StringBuilder.Chars%2A> per eseguire l'accesso basato su indice a uno o un numero limitato di caratteri ha un impatto trascurabile sulle prestazioni, in genere è un'operazione **0(n)**. L'impatto significativo sulle prestazioni si verifica durante l'iterazione dei caratteri nell'oggetto <xref:System.Text.StringBuilder>, che è un'operazione **O(n^2)**. 

Se si verificano problemi di prestazioni quando si usa l'indicizzazione basata su caratteri con gli oggetti <xref:System.Text.StringBuilder>, è possibile adottare una delle seguenti soluzioni alternative:

- Convertire l'istanza <xref:System.Text.StringBuilder> in un <xref:System.String> chiamando il metodo <xref:System.Text.StringBuilder.ToString%2A>, quindi accedere ai caratteri nella stringa.

- Copiare il contenuto dell'oggetto <xref:System.Text.StringBuilder> esistente in un nuovo oggetto <xref:System.Text.StringBuilder> con dimensioni preimpostate. Le prestazioni migliorano perché il nuovo oggetto <xref:System.Text.StringBuilder> non è pesante. Ad esempio:

   ```csharp
   // sbOriginal is the existing StringBuilder object
   var sbNew = new StringBuilder(sbOriginal.ToString(), sbOriginal.Length);
   ```
   ```vb
   ' sbOriginal is the existing StringBuilder object
   Dim sbNew = New StringBuilder(sbOriginal.ToString(), sbOriginal.Length)
   ```
- Impostare la capacità iniziale dell'oggetto <xref:System.Text.StringBuilder> su un valore approssimativamente uguale alle dimensioni massime previste chiamando il costruttore <xref:System.Text.StringBuilder.%23ctor(System.Int32)>. Si noti che in questo modo viene allocato l'intero di memoria anche se <xref:System.Text.StringBuilder> raramente raggiunge la capacità massima.
