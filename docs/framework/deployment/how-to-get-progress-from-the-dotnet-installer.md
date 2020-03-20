---
title: "Procedura: ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5"
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- progress information, .NET Framework installer
- .NET Framework, installing
ms.assetid: 0a1a3ba3-7e46-4df2-afd3-f3a8237e1c4f
ms.openlocfilehash: cd81ad83aee80341d0334cfa8caa165b25ee0564
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75716494"
---
# <a name="how-to-get-progress-from-the-net-framework-45-installer"></a>Procedura: ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5

.NET Framework 4.5 è un runtime ridistribuibile. Se si sviluppano app per questa versione di .NET Framework, è possibile includere (a catena) l'installazione di .NET Framework 4.5 come componente prerequisito nell'installazione dell'app. Per offrire un'esperienza d'installazione personalizzata o unificata, è consigliabile avviare l'installazione di .NET Framework 4.5 n modo invisibile all'utente e tenere traccia dello stato di avanzamento visualizzando l'avanzamento dell'installazione dell'app. Per abilitare la gestione invisibile all'utente, l'installazione di .NET Framework 4.5, che può essere controllata, definisce un protocollo usando un segmento di I/O mappato alla memoria (MMIO) per comunicare con l'installazione, vale a dire con il watcher o il chainer. Questo protocollo definisce come un chainer può ottenere informazioni sullo stato di avanzamento, ottenere risultati dettagliati, rispondere ai messaggi e annullare l'installazione di .NET Framework 4.5.

- **Invocazione**. Per chiamare l'installazione di .NET Framework 4.5 e ricevere informazioni sullo stato di avanzamento della sezione MMIO, il programma di installazione deve eseguire le operazioni seguenti:

    1. Chiamare il programma ridistribuibile di .NET Framework 4.5:

        `dotNetFx45_Full_x86_x64.exe /q /norestart /pipe section-name`

        Dove *section name* è il nome che si vuole usare per identificare l'app. Poiché l'installazione di .NET Framework legge e scrive in modo asincrono nella sezione MIMO, potrebbe essere utile usare eventi e messaggi in quell'intervallo di tempo. Nell'esempio il processo di installazione di .NET Framework viene creato da un costruttore che alloca la sezione MMIO (`TheSectionName`) e definisce un evento (`TheEventName`):

        ```cpp
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName")
        ```

        Sostituire i nomi con nomi univoci per il programma di installazione.

    2. Leggere dalla sezione MMIO. In .NET Framework 4.5. Di conseguenza, lo stato di avanzamento viene restituito, ovvero scritto, nella sezione MMIO come due numeri (`m_downloadSoFar` e `m_installSoFar`) crescenti da 0 a 255. Quando viene scritto 255 e viene chiuso .NET Framework, l'installazione è completa.

- **Codici di uscita**. I codici di uscita seguenti del comando per la chiamata al programma ridistribuibile .NET Framework 4.5 indicano se l'installazione è riuscita o meno:

  - 0: installazione completata.

  - 3010: installazione completata; è necessario un riavvio del sistema.

  - 1602: l'installazione è stata annullata.

  - Tutti gli altri codici: si sono verificati errori durante l'installazione; esaminare i file di log creati in %temp% per informazioni dettagliate.

- **Annullamento dell'installazione**. È possibile annullare l'installazione in qualsiasi momento usando il metodo `Abort` per impostare i flag `m_downloadAbort` e `m_ installAbort` nella sezione MMIO.

## <a name="chainer-sample"></a>Esempio di chainer

L'esempio di Chainer avvia l'installazione di .NET Framework 4.5 in modo invisibile all'utente e tiene traccia dello stato di avanzamento. Questo esempio è simile all'esempio di chainer di .NET Framework 4. Tuttavia, in questo caso, è possibile evitare i riavvii del sistema elaborando la finestra di messaggio per chiudere le app di .NET Framework 4. Per informazioni sulla finestra di messaggio, vedere [Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5](reducing-system-restarts.md). L'esempio può essere usato con il programma di installazione di .NET Framework 4, In questo caso, il messaggio non viene inviato.

> [!WARNING]
> È necessario eseguire l'esempio come amministratore.

È possibile scaricare la soluzione Visual Studio completa per l'[esempio di chainer di .NET Framework 4.5](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba) dalla raccolta di esempi di MSDN.

Le sezioni seguenti descrivono i file significativi in questo esempio: MMIOChainer.h, ChainingdotNet4.cpp e IProgressObserver.h.

#### <a name="mmiochainerh"></a>MMIOChainer.h

- Il file MMIOChainer.h (vedere il [codice completo](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=663039622)) contiene la definizione della struttura dei dati e la classe di base dalla quale deve essere derivata la classe del chainer. .NET Framework 4.5 estende la struttura dei dati MMIO per gestire i dati necessari al programma di installazione di .NET Framework 4.5. Poiché le modifiche alla struttura MMIO sono compatibili con le versioni precedenti, un chainer di .NET Framework 4 può essere usato con l'installazione di .NET Framework 4.5 senza richiedere una ricompilazione. Tuttavia, questo scenario non supporta la funzionalità per ridurre il numero di riavvii del sistema.

    Un campo della versione consente di identificare le revisioni alla struttura e al formato dei messaggi. L'installazione di .NET Framework determina la versione dell'interfaccia del chainer chiamando la funzione `VirtualQuery` per determinare la dimensione del mapping del file. Se la dimensione è abbastanza grande per contenere il campo della versione, l'installazione di .NET Framework usa il valore specificato. Se il mapping del file è troppo piccolo per contenere un campo della versione, come avviene nel caso di .NET Framework 4, il processo di installazione presuppone che la versione sia la versione 0 (4). Se il chainer non supporta la versione del messaggio che l'installazione di .NET Framework vuole inviare, l'installazione di .NET Framework presuppone una risposta Ignora.

    La struttura dei dati MMIO è definita come segue:

    ```cpp
    // MMIO data structure for interprocess communication
        struct MmioDataStructure
        {
            bool m_downloadFinished;               // Is download complete?
            bool m_installFinished;                // Is installation complete?
            bool m_downloadAbort;                  // Set to cause downloader to abort.
            bool m_installAbort;                   // Set to cause installer to abort.
            HRESULT m_hrDownloadFinished;          // Resulting HRESULT for download.
            HRESULT m_hrInstallFinished;           // Resulting HRESULT for installation.
            HRESULT m_hrInternalError;
            WCHAR m_szCurrentItemStep[MAX_PATH];
            unsigned char m_downloadSoFar;         // Download progress 0-255 (0-100% done).
            unsigned char m_installSoFar;          // Installation progress 0-255 (0-100% done).
            WCHAR m_szEventName[MAX_PATH];         // Event that chainer creates and chainee opens to sync communications.

            BYTE m_version;                        // Version of the data structure, set by chainer:
                                                   // 0x0: .NET Framework 4
                                                   // 0x1: .NET Framework 4.5

            DWORD m_messageCode;                   // Current message sent by the chainee; 0 if no message is active.
            DWORD m_messageResponse;               // Chainer's response to current message; 0 if not yet handled.
            DWORD m_messageDataLength;             // Length of the m_messageData field, in bytes.
            BYTE m_messageData[1];                 // Variable-length buffer; content depends on m_messageCode.
        };
    ```

- La struttura dei dati `MmioDataStructure` non deve essere usata direttamente; usare invece la classe `MmioChainer` per implementare il chainer. Derivare dalla classe `MmioChainer` per concatenare il programma ridistribuibile .NET Framework 4.5.

#### <a name="iprogressobserverh"></a>IProgressObserver.h

- Il file IProgressObserver.h file implementa un osservatore dello stato di avanzamento (vedere il [codice completo](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1263700592)). L'osservatore riceve notifica dello stato di avanzamento del download e dell'installazione (specificato come `char` senza segno, da 0 a 255, che indica il completamento dall'1% al 100%). L'osservatore riceve anche la notifica dell'invio di un messaggio da parte del chainer e invia una risposta.

    ```cpp
        class IProgressObserver
        {
        public:
            virtual void OnProgress(unsigned char) = 0; // 0 - 255:  255 == 100%
            virtual void Finished(HRESULT) = 0;         // Called when operation is complete
            virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength) = 0; // Called when a message is sent
        };
    ```

#### <a name="chainingdotnet45cpp"></a>ChainingdotNet4.5.cpp

- Il file [ChainingdotNet4.5.cpp](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1757268882) implementa la classe `Server`, derivata dalla classe `MmioChainer` ed esegue l'override dei metodi appropriati per visualizzare le informazioni sullo stato di avanzamento. MmioChainer crea una sezione con il nome specificato e inizializza il chainer con il nome dell'evento specificato. Il nome dell'evento viene salvato nella struttura dei dati mappata. Specificare nomi di sezione ed evento univoci. La classe `Server` nel codice seguente avvia il programma di installazione specificato, esegue il monitoraggio dello stato di avanzamento e restituisce un codice di uscita.

    ```cpp
    class Server : public ChainerSample::MmioChainer, public ChainerSample::IProgressObserver
    {
    public:
        …………….
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName") //customize for your event names
        {}
    ```

    L'installazione viene avviata nel metodo Main.

    ```cpp
    // Main entry point for program
    int __cdecl main(int argc, _In_count_(argc) char **_argv)
    {
        int result = 0;
        CString args;
        if (argc > 1)
        {
            args = CString(_argv[1]);
        }

        if (IsNetFx4Present(NETFX45_RC_REVISION))
        {
            printf(".NET Framework 4.5 is already installed");
        }
        else
        {
            result = Server().Launch(args);
        }

        return result;
    }
    ```

- Prima di avviare l'installazione, il chainer verifica se .NET Framework 4.5 è già installato eseguendo una chiamata a `IsNetFx4Present`:

    ```cpp
    ///  Checks for presence of the .NET Framework 4.
    ///    A value of 0 for dwMinimumRelease indicates a check for the .NET Framework 4 full
    ///    Any other value indicates a check for a specific compatible release of the .NET Framework 4.
    #define NETFX40_FULL_REVISION 0
    // TODO: Replace with released revision number
    #define NETFX45_RC_REVISION MAKELONG(50309, 5)   // .NET Framework 4.5
    bool IsNetFx4Present(DWORD dwMinimumRelease)
    {
        DWORD dwError = ERROR_SUCCESS;
        HKEY hKey = NULL;
        DWORD dwData = 0;
        DWORD dwType = 0;
        DWORD dwSize = sizeof(dwData);

        dwError = ::RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full", 0, KEY_READ, &hKey);
        if (ERROR_SUCCESS == dwError)
        {
            dwError = ::RegQueryValueExW(hKey, L"Release", 0, &dwType, (LPBYTE)&dwData, &dwSize);

            if ((ERROR_SUCCESS == dwError) && (REG_DWORD != dwType))
            {
                dwError = ERROR_INVALID_DATA;
            }
            else if (ERROR_FILE_NOT_FOUND == dwError)
            {
                // Release value was not found, let's check for 4.0.
                dwError = ::RegQueryValueExW(hKey, L"Install", 0, &dwType, (LPBYTE)&dwData, &dwSize);

                // Install = (REG_DWORD)1;
                if ((ERROR_SUCCESS == dwError) && (REG_DWORD == dwType) && (dwData == 1))
                {
                    // treat 4.0 as Release = 0
                    dwData = 0;
                }
                else
                {
                    dwError = ERROR_INVALID_DATA;
                }
            }
        }

        if (hKey != NULL)
        {
            ::RegCloseKey(hKey);
        }

        return ((ERROR_SUCCESS == dwError) && (dwData >= dwMinimumRelease));
    }
    ```

- È possibile modificare il percorso del file eseguibile (Setup.exe nell'esempio) nel metodo `Launch` per puntare alla posizione corretta oppure personalizzare il codice per determinare la posizione. La classe di base `MmioChainer` offre un metodo `Run()` di blocco chiamato dalla classe derivata.

    ```cpp
    bool Launch(const CString& args)
    {
    CString cmdline = L"dotNetFx45_Full_x86_x64.exe -pipe TheSectionName " + args; // Customize with name and location of setup .exe that you want to run
    STARTUPINFO si = {0};
    si.cb = sizeof(si);
    PROCESS_INFORMATION pi = {0};

    // Launch the Setup.exe that installs the .NET Framework 4.5
    BOOL bLaunchedSetup = ::CreateProcess(NULL,
     cmdline.GetBuffer(),
     NULL, NULL, FALSE, 0, NULL, NULL,
     &si,
     &pi);

    // If successful
    if (bLaunchedSetup != 0)
    {
    IProgressObserver& observer = dynamic_cast<IProgressObserver&>(*this);
    Run(pi.hProcess, observer);

    ……………………..
    return (bLaunchedSetup != 0);
    }
    ```

- Il metodo `Send` intercetta ed elabora i messaggi. In questa versione di .NET Framework l'unico messaggio supportato è il messaggio di chiusura dell'applicazione.

    ```cpp
            // SendMessage
            //
            // Send a message and wait for the response.
            // dwMessage: Message to send
            // pData: The buffer to copy the data to
            // dwDataLength: Initially a pointer to the size of pBuffer. Upon successful call, the number of bytes copied to pBuffer.
            //--------------------------------------------------------------
        virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength)
        {
            DWORD dwResult = 0;
            printf("received message: %d\n", dwMessage);
            // Handle message
            switch (dwMessage)
            {
            case MMIO_CLOSE_APPS:
                {
                    printf("    applications are holding files in use:\n");
                    IronMan::MmioCloseApplications* applications = reinterpret_cast<IronMan::MmioCloseApplications*>(pData);
                    for(DWORD i = 0; i < applications->m_dwApplicationsSize; i++)
                    {
                        printf("      %ls (%d)\n", applications->m_applications[i].m_szName, applications->m_applications[i].m_dwPid);
                    }

                    printf("    should appliations be closed? (Y)es, (N)o, (R)efresh : ");
                    while (dwResult == 0)
                    {
                        switch (toupper(getwchar()))
                        {
                        case 'Y':
                            dwResult = IDYES;  // Close apps
                            break;
                        case 'N':
                            dwResult = IDNO;
                            break;
                        case 'R':
                            dwResult = IDRETRY;
                            break;
                        }
                    }
                    printf("\n");
                    break;
                }
            default:
                break;
            }
            printf("  response: %d\n  ", dwResult);
            return dwResult;
        }
    };
    ```

- I dati dello stato di avanzamento sono costituiti da un `char` senza segno compreso tra 0 (0%) e 255 (100%).

    ```cpp
    private: // IProgressObserver
        virtual void OnProgress(unsigned char ubProgressSoFar)
        {…………
       }
    ```

- HRESULT viene passato al metodo `Finished`.

    ```cpp
    virtual void Finished(HRESULT hr)
    {
    // This HRESULT is communicated over MMIO and may be different than process
    // Exit code of the Chainee Setup.exe itself
    printf("\r\nFinished HRESULT: 0x%08X\r\n", hr);
    }
    ```

    > [!IMPORTANT]
    > Il programma ridistribuibile .NET Framework 4.5 scrive in genere molti messaggi sullo stato di avanzamento e un unico messaggio per indicarne il completamento (sul lato del chainer). La lettura viene eseguita in modo asincrono cercando i record `Abort`. Se viene ricevuto un record `Abort`, l'installazione viene annullata e il programma scrive un record completato con i dati E_ABORT dopo che l'installazione è stata interrotta ed è stato eseguito il rollback delle operazioni di installazione.

Un server tipico crea un nome file MMIO casuale, crea il file (come illustrato nell'esempio di codice precedente in `Server::CreateSection`) e avvia il programma ridistribuibile usando il metodo `CreateProcess` e passando il nome pipe con l'opzione `-pipe someFileSectionName`. Il server deve implementare il metodi `OnProgress`, `Send` e `Finished` con il codice specifico dall'interfaccia utente dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Guida alla distribuzione per gli sviluppatori](deployment-guide-for-developers.md)
- [Distribuzione](index.md)
