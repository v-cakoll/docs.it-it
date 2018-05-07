---
title: 'Procedura: creare un servizio flusso di lavoro che chiama un altro servizio flusso di lavoro'
ms.date: 03/30/2017
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
ms.openlocfilehash: fda5a7286c3d20c7cdc2093e58bfe3fbdcf1d1c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a>Procedura: creare un servizio flusso di lavoro che chiama un altro servizio flusso di lavoro
Per un servizio di flusso di lavoro è talvolta necessario ottenere informazioni da un altro servizio analogo.  In questo argomento viene illustrato come eseguire chiamate tra servizi di flusso di lavoro. Verranno creati due servizi di flusso di lavoro: uno che dispone di un metodo che inverte la stringa di input e l'altro che converte la stringa di input in caratteri maiuscoli dopo aver invertito la stringa utilizzata dal primo servizio.  
  
### <a name="to-create-the-reverser-workflow-service"></a>Per creare il servizio di flusso di lavoro che esegue l'inversione  
  
1.  Eseguire [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] come amministratore.  
  
2.  Selezionare **File**, **nuovo progetto**. Sotto il **flusso di lavoro** nodo il **modelli installati** riquadro, selezionare **applicazione del servizio del flusso di lavoro WCF**. Denominare la soluzione `NestedServices` e quindi fare clic su **OK**.  
  
3.  In **server**, assicurarsi che **Usa Server Web IIS locale** è selezionata. Fare clic su **crea Directory virtuale**. Fare clic su **OK** nella finestra di dialogo Conferma che la directory virtuale è stata creata.  
  
4.  In Esplora soluzioni rinominare Service1. xamlx in `StringReverserService.xamlx`.  
  
5.  Nel **le proprietà del progetto** pagina per il nuovo progetto, fare clic su di **Web** scheda. Impostare il **azione di avvio** a **pagina specifica**e selezionare stringreverserservice. Xamlx come pagina di avvio.  
  
6.  Aprire StringReverserService.xamlx nella finestra di progettazione, eliminare le attività `ReceiveRequest` e `SendReply` esistenti, quindi trascinare un'attività `ReceiveAndSendReply` nell'attività Sequence esistente.  
  
    1.  Impostare il **OperationName** su ReverseString.  
  
    2.  Impostare il **ServiceContractName** su IReverseString.  
  
    3.  Selezionare il **CanCreateInstance** casella di controllo.  
  
7.  Selezionare il **SequentialService** attività e quindi scegliere il **variabili** scheda nella parte inferiore della finestra di progettazione. Creare due nuove variabili di tipo String denominate StringToReverse e ReversedStringToReturn.  
  
8.  Fare clic su di **definire** collegare il **ricezione** attività. Fare clic su di **parametri**, quindi creare un parametro denominato InputString di tipo String da assegnare a StringToReverse.  
  
9. Fare clic su di **Definisci** collegare il **SendReplyToReceive** attività. Fare clic su di **parametri**, quindi creare un parametro denominato ReversedString di tipo String assegnato a ReversedStringToReturn.  
  
10. Per implementare la logica per il servizio, creare una nuova classe nel progetto denominata StringLibrary.  Sostituire la definizione della classe con il codice seguente.  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
    ```  
  
11. Per chiamare il metodo ReverseString sull'input, trascinare un **InvokeMethod** attività dalla casella degli strumenti per lo spazio tra il **ricezione** e **SendReply** le attività. Impostare le proprietà dell'attività come indicato di seguito.  
  
    1.  **NomeMetodo**: ReverseString  
  
    2.  **Risultato**: ReversedStringToReturn  
  
    3.  **I parametri**: creare un nuovo parametro con un **direzione** di In, una **tipo** della stringa e una **valore** stringtoreverse.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
12. Premere F5 per testare il servizio. Nel client di test WCF visualizzato fare doppio clic sul metodo ReverseString(). Nel riquadro della richiesta, immettere `Sample` per il valore del parametro InputString. Fare clic su **richiamare**. Il servizio deve restituire "elpmaS".  
  
### <a name="to-create-the-uppercaser-workflow-service"></a>Per creare il servizio di flusso di lavoro che esegue la conversione in caratteri maiuscoli  
  
1.  Fare clic sul progetto NestedServices e selezionare **Aggiungi**, **nuovo elemento**. Nel **flusso di lavoro** nodo, seleziona **servizio flusso di lavoro WCF**e il nome del nuovo servizio `UpperCaserService`. Fare clic su **Aggiungi**. Un nuovo servizio di flusso di lavoro denominato UpperCaserService.xamlx verrà aggiunto al progetto.  
  
2.  Aprire Uppercaserservice nella finestra di progettazione e di eliminare quello esistente **ReceiveRequest** e `SendReply` attività e trascinare un `ReceiveAndSendReply` attività nell'attività sequence esistente.  
  
    1.  Impostare il **OperationName** su UpperCaseString.  
  
    2.  Impostare il **ServiceContractName** su IUpperCaseString.  
  
    3.  Selezionare il **CanCreateInstance** casella di controllo.  
  
3.  Selezionare l'attività SequentialService e quindi fare clic su di **variabili** scheda nella parte inferiore della finestra di progettazione. Creare tre nuove variabili di tipo String, denominate StringToUpper, StringToReverse e StringToReturn.  
  
4.  Fare clic su di **definire** collegare il **ricezione** attività. Fare clic su di **parametri**, quindi creare un parametro denominato InputString di tipo String da assegnare a StringToUpper.  
  
5.  Fare clic su di **Definisci** collegare il **SendReplyToReceive** attività. Fare clic su di **parametri**, quindi creare un parametro denominato ModifiedString di tipo String assegnato a StringToReturn.  
  
6.  Per implementare la logica per il servizio, creare un nuovo metodo nella classe StringLibrary tramite il codice seguente.  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
    ```  
  
7.  Per chiamare il metodo UpperCaseString sull'input, trascinare un **InvokeMethod** attività dalla casella degli strumenti per lo spazio tra il **ricezione** e **SendReply** le attività. Impostare le proprietà dell'attività come indicato di seguito.  
  
    1.  **NomeMetodo**: UpperCaseString  
  
    2.  **Risultato**: StringToReverse  
  
    3.  **I parametri**: creare un nuovo parametro con un **direzione** di In, una **tipo** della stringa e una **valore** stringtoupper.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
8.  A questo punto verrà chiamato il primo servizio sulla stringa modificata. Fare clic sul progetto e selezionare **Aggiungi riferimento al servizio**. Aggiungere un riferimento al servizio su http://localhost/NestedServices/StringReverserService.xamlx . sln e compilare il progetto per creare un'attività personalizzata per accedere al primo servizio Web.  
  
9. Trascinare un'istanza della nuova attività flusso di lavoro, tra il **InvokeMethod** attività e **SendReplyToReceive** le attività. Assegnare la variabile StringToReverse alla proprietà InputString della nuova attività e la variabile StringToReturn alla proprietà StringToReturn.  
  
10. Aprire la pagina delle proprietà per il progetto NestedServices e modificare il **pagina specifica** nel **Web** scheda Uppercaserservice.  
  
11. Premere F5 per testare il servizio. Nel client di test WCF visualizzato fare doppio clic sul metodo ReverseString(). Nel riquadro della richiesta, immettere `Sample` per il valore del parametro InputString. Fare clic su **richiamare**. Il servizio deve restituire "ELPMAS".  
  
### <a name="to-create-a-client-to-call-the-services"></a>Per creare un client che chiami i servizi  
  
1.  Aggiungere un nuovo progetto di applicazione console denominato Client alla soluzione.  
  
2.  Fare clic sul progetto Client e selezionare **Aggiungi riferimento al servizio**. Nella finestra visualizzata, fare clic su **Discover**. Selezionare StringReverserService.xamlx e immettere ReverseService come spazio dei nomi.  Fare clic su **OK**.  
  
3.  Sostituire il metodo Main in Program.cs con il codice seguente.  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
    ```
