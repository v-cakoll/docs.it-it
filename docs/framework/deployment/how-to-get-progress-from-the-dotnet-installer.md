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
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716494"
---
# <a name="how-to-get-progress-from-the-net-framework-45-installer"></a><span data-ttu-id="d64e4-102">Procedura: ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d64e4-102">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>

<span data-ttu-id="d64e4-103">.NET Framework 4.5 è un runtime ridistribuibile.</span><span class="sxs-lookup"><span data-stu-id="d64e4-103">The .NET Framework 4.5 is a redistributable runtime.</span></span> <span data-ttu-id="d64e4-104">Se si sviluppano app per questa versione di .NET Framework, è possibile includere (a catena) l'installazione di .NET Framework 4.5 come componente prerequisito nell'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="d64e4-104">If you develop apps for this version of the .NET Framework, you can include (chain) .NET Framework 4.5 setup as a prerequisite part of your app's setup.</span></span> <span data-ttu-id="d64e4-105">Per offrire un'esperienza d'installazione personalizzata o unificata, è consigliabile avviare l'installazione di .NET Framework 4.5 n modo invisibile all'utente e tenere traccia dello stato di avanzamento visualizzando l'avanzamento dell'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="d64e4-105">To present a customized or unified setup experience, you may want to silently launch .NET Framework 4.5 setup and track its progress while showing your app's setup progress.</span></span> <span data-ttu-id="d64e4-106">Per abilitare la gestione invisibile all'utente, l'installazione di .NET Framework 4.5, che può essere controllata, definisce un protocollo usando un segmento di I/O mappato alla memoria (MMIO) per comunicare con l'installazione, vale a dire con il watcher o il chainer.</span><span class="sxs-lookup"><span data-stu-id="d64e4-106">To enable silent tracking, .NET Framework 4.5 setup (which can be watched) defines a protocol by using a memory-mapped I/O (MMIO) segment to communicate with your setup (the watcher or chainer).</span></span> <span data-ttu-id="d64e4-107">Questo protocollo definisce come un chainer può ottenere informazioni sullo stato di avanzamento, ottenere risultati dettagliati, rispondere ai messaggi e annullare l'installazione di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="d64e4-107">This protocol defines a way for a chainer to obtain progress information, get detailed results, respond to messages, and cancel the .NET Framework 4.5 setup.</span></span>

- <span data-ttu-id="d64e4-108">**Chiamata**.</span><span class="sxs-lookup"><span data-stu-id="d64e4-108">**Invocation**.</span></span> <span data-ttu-id="d64e4-109">Per chiamare l'installazione di .NET Framework 4.5 e ricevere informazioni sullo stato di avanzamento della sezione MMIO, il programma di installazione deve eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d64e4-109">To call .NET Framework 4.5 setup and receive progress information from the MMIO section, your setup program must do the following:</span></span>

    1. <span data-ttu-id="d64e4-110">Chiamare il programma ridistribuibile .NET Framework 4,5:</span><span class="sxs-lookup"><span data-stu-id="d64e4-110">Call the .NET Framework 4.5 redistributable program:</span></span>

        `dotNetFx45_Full_x86_x64.exe /q /norestart /pipe section-name`

        <span data-ttu-id="d64e4-111">Dove *section name* è il nome che si vuole usare per identificare l'app.</span><span class="sxs-lookup"><span data-stu-id="d64e4-111">Where *section name* is any name you want to use to identify your app.</span></span> <span data-ttu-id="d64e4-112">Poiché l'installazione di .NET Framework legge e scrive in modo asincrono nella sezione MIMO, potrebbe essere utile usare eventi e messaggi in quell'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d64e4-112">.NET Framework setup reads and writes to the MMIO section asynchronously, so you might find it convenient to use events and messages during that time.</span></span> <span data-ttu-id="d64e4-113">Nell'esempio il processo di installazione di .NET Framework viene creato da un costruttore che alloca la sezione MMIO (`TheSectionName`) e definisce un evento (`TheEventName`):</span><span class="sxs-lookup"><span data-stu-id="d64e4-113">In the example, the .NET Framework setup process is created by a constructor that both allocates the MMIO section (`TheSectionName`) and defines an event (`TheEventName`):</span></span>

        ```cpp
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName")
        ```

        <span data-ttu-id="d64e4-114">Sostituire i nomi con nomi univoci per il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="d64e4-114">Please replace those names with names that are unique to your setup program.</span></span>

    2. <span data-ttu-id="d64e4-115">Leggere dalla sezione MMIO.</span><span class="sxs-lookup"><span data-stu-id="d64e4-115">Read from the MMIO section.</span></span> <span data-ttu-id="d64e4-116">Nel .NET Framework 4,5, le operazioni di download e installazione sono simultanee: una parte del .NET Framework potrebbe essere installata mentre è in corso il download di un'altra parte.</span><span class="sxs-lookup"><span data-stu-id="d64e4-116">In the .NET Framework 4.5, the download and installation operations are simultaneous: One part of the .NET Framework might be installing while another part is downloading.</span></span> <span data-ttu-id="d64e4-117">Di conseguenza, lo stato di avanzamento viene restituito, ovvero scritto, nella sezione MMIO come due numeri (`m_downloadSoFar` e `m_installSoFar`) crescenti da 0 a 255.</span><span class="sxs-lookup"><span data-stu-id="d64e4-117">As a result, progress is sent back (that is, written) to the MMIO section as two numbers (`m_downloadSoFar` and `m_installSoFar`) that increase from 0 to 255.</span></span> <span data-ttu-id="d64e4-118">Quando viene scritto 255 e viene chiuso .NET Framework, l'installazione è completa.</span><span class="sxs-lookup"><span data-stu-id="d64e4-118">When 255 is written and the .NET Framework exits, the installation is complete.</span></span>

- <span data-ttu-id="d64e4-119">**Codici di uscita**.</span><span class="sxs-lookup"><span data-stu-id="d64e4-119">**Exit codes**.</span></span> <span data-ttu-id="d64e4-120">I codici di uscita seguenti del comando per la chiamata al programma ridistribuibile .NET Framework 4.5 indicano se l'installazione è riuscita o meno:</span><span class="sxs-lookup"><span data-stu-id="d64e4-120">The following exit codes from the command to call the .NET Framework 4.5 redistributable program indicate whether setup has succeeded or failed:</span></span>

  - <span data-ttu-id="d64e4-121">0: installazione completata.</span><span class="sxs-lookup"><span data-stu-id="d64e4-121">0 - Setup completed successfully.</span></span>

  - <span data-ttu-id="d64e4-122">3010: installazione completata; è necessario un riavvio del sistema.</span><span class="sxs-lookup"><span data-stu-id="d64e4-122">3010 – Setup completed successfully; a system restart is required.</span></span>

  - <span data-ttu-id="d64e4-123">1602: l'installazione è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="d64e4-123">1602 – Setup has been canceled.</span></span>

  - <span data-ttu-id="d64e4-124">Tutti gli altri codici: si sono verificati errori durante l'installazione; esaminare i file di log creati in %temp% per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="d64e4-124">All other codes - Setup encountered errors; examine the log files created in %temp% for details.</span></span>

- <span data-ttu-id="d64e4-125">**Annullamento dell'installazione**.</span><span class="sxs-lookup"><span data-stu-id="d64e4-125">**Canceling setup**.</span></span> <span data-ttu-id="d64e4-126">È possibile annullare l'installazione in qualsiasi momento usando il metodo `Abort` per impostare i flag `m_downloadAbort` e `m_ installAbort` nella sezione MMIO.</span><span class="sxs-lookup"><span data-stu-id="d64e4-126">You can cancel setup at any time by using the `Abort` method to set the `m_downloadAbort` and `m_ installAbort` flags in the MMIO section.</span></span>

## <a name="chainer-sample"></a><span data-ttu-id="d64e4-127">Esempio di chainer</span><span class="sxs-lookup"><span data-stu-id="d64e4-127">Chainer Sample</span></span>

<span data-ttu-id="d64e4-128">L'esempio di Chainer avvia l'installazione di .NET Framework 4.5 in modo invisibile all'utente e tiene traccia dello stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="d64e4-128">The Chainer sample silently launches and tracks .NET Framework 4.5 setup while showing progress.</span></span> <span data-ttu-id="d64e4-129">Questo esempio è simile all'esempio di chainer di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d64e4-129">This sample is similar to the Chainer sample provided for the .NET Framework 4.</span></span> <span data-ttu-id="d64e4-130">Tuttavia, in questo caso, è possibile evitare i riavvii del sistema elaborando la finestra di messaggio per chiudere le app di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d64e4-130">However, in addition, it can avoid system restarts by processing the message box for closing .NET Framework 4 apps.</span></span> <span data-ttu-id="d64e4-131">Per informazioni sulla finestra di messaggio, vedere [Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5](reducing-system-restarts.md).</span><span class="sxs-lookup"><span data-stu-id="d64e4-131">For information about this message box, see [Reducing System Restarts During .NET Framework 4.5 Installations](reducing-system-restarts.md).</span></span> <span data-ttu-id="d64e4-132">L'esempio può essere usato con il programma di installazione di .NET Framework 4, In questo caso, il messaggio non viene inviato.</span><span class="sxs-lookup"><span data-stu-id="d64e4-132">You can use this sample with the .NET Framework 4 installer; in that scenario, the message is simply not sent.</span></span>

> [!WARNING]
> <span data-ttu-id="d64e4-133">È necessario eseguire l'esempio come amministratore.</span><span class="sxs-lookup"><span data-stu-id="d64e4-133">You must run the example as an administrator.</span></span>

<span data-ttu-id="d64e4-134">È possibile scaricare la soluzione Visual Studio completa per l'[esempio di chainer di .NET Framework 4.5](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba) dalla raccolta di esempi di MSDN.</span><span class="sxs-lookup"><span data-stu-id="d64e4-134">You can download the complete Visual Studio solution for the [.NET Framework 4.5 Chainer Sample](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba) from the MSDN Samples Gallery.</span></span>

<span data-ttu-id="d64e4-135">Le sezioni seguenti descrivono i file significativi in questo esempio: MMIOChainer.h, ChainingdotNet4.cpp e IProgressObserver.h.</span><span class="sxs-lookup"><span data-stu-id="d64e4-135">The following sections describe the significant files in this sample: MMIOChainer.h, ChainingdotNet4.cpp, and IProgressObserver.h.</span></span>

#### <a name="mmiochainerh"></a><span data-ttu-id="d64e4-136">MMIOChainer.h</span><span class="sxs-lookup"><span data-stu-id="d64e4-136">MMIOChainer.h</span></span>

- <span data-ttu-id="d64e4-137">Il file MMIOChainer.h (vedere il [codice completo](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=663039622)) contiene la definizione della struttura dei dati e la classe di base dalla quale deve essere derivata la classe del chainer.</span><span class="sxs-lookup"><span data-stu-id="d64e4-137">The MMIOChainer.h file (see [complete code](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=663039622)) contains the data structure definition and the base class from which the chainer class should be derived.</span></span> <span data-ttu-id="d64e4-138">.NET Framework 4.5 estende la struttura dei dati MMIO per gestire i dati necessari al programma di installazione di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="d64e4-138">The .NET Framework 4.5 extends the MMIO data structure to handle data that the .NET Framework 4.5 installer needs.</span></span> <span data-ttu-id="d64e4-139">Poiché le modifiche alla struttura MMIO sono compatibili con le versioni precedenti, un chainer di .NET Framework 4 può essere usato con l'installazione di .NET Framework 4.5 senza richiedere una ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="d64e4-139">The changes to the MMIO structure are backward-compatible, so a .NET Framework 4 chainer can work with .NET Framework 4.5 setup without requiring recompilation.</span></span> <span data-ttu-id="d64e4-140">Tuttavia, questo scenario non supporta la funzionalità per ridurre il numero di riavvii del sistema.</span><span class="sxs-lookup"><span data-stu-id="d64e4-140">However, this scenario does not support the feature for reducing system restarts.</span></span>

    <span data-ttu-id="d64e4-141">Un campo della versione consente di identificare le revisioni alla struttura e al formato dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="d64e4-141">A version field provides a means of identifying revisions to the structure and message format.</span></span> <span data-ttu-id="d64e4-142">L'installazione di .NET Framework determina la versione dell'interfaccia del chainer chiamando la funzione `VirtualQuery` per determinare la dimensione del mapping del file.</span><span class="sxs-lookup"><span data-stu-id="d64e4-142">The .NET Framework setup determines the version of the chainer interface by calling the `VirtualQuery` function to determine the size of the file mapping.</span></span> <span data-ttu-id="d64e4-143">Se la dimensione è abbastanza grande per contenere il campo della versione, l'installazione di .NET Framework usa il valore specificato.</span><span class="sxs-lookup"><span data-stu-id="d64e4-143">If the size is large enough to accommodate the version field, .NET Framework setup uses the specified value.</span></span> <span data-ttu-id="d64e4-144">Se il mapping del file è troppo piccolo per contenere un campo della versione, come avviene nel caso di .NET Framework 4, il processo di installazione presuppone che la versione sia la versione 0 (4).</span><span class="sxs-lookup"><span data-stu-id="d64e4-144">If the file mapping is too small to contain a version field, which is the case with the .NET Framework 4, the setup process assumes version 0 (4).</span></span> <span data-ttu-id="d64e4-145">Se il chainer non supporta la versione del messaggio che l'installazione di .NET Framework vuole inviare, l'installazione di .NET Framework presuppone una risposta Ignora.</span><span class="sxs-lookup"><span data-stu-id="d64e4-145">If the chainer does not support the version of the message that .NET Framework setup wants to send, .NET Framework setup assumes an ignore response.</span></span>

    <span data-ttu-id="d64e4-146">La struttura dei dati MMIO è definita come segue:</span><span class="sxs-lookup"><span data-stu-id="d64e4-146">The MMIO data structure is defined as follows:</span></span>

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

- <span data-ttu-id="d64e4-147">La struttura dei dati `MmioDataStructure` non deve essere usata direttamente; usare invece la classe `MmioChainer` per implementare il chainer.</span><span class="sxs-lookup"><span data-stu-id="d64e4-147">The `MmioDataStructure` data structure should not be used directly; use the `MmioChainer` class instead to implement your chainer.</span></span> <span data-ttu-id="d64e4-148">Derivare dalla classe `MmioChainer` per concatenare il programma ridistribuibile .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="d64e4-148">Derive from the `MmioChainer` class to chain the .NET Framework 4.5 redistributable.</span></span>

#### <a name="iprogressobserverh"></a><span data-ttu-id="d64e4-149">IProgressObserver.h</span><span class="sxs-lookup"><span data-stu-id="d64e4-149">IProgressObserver.h</span></span>

- <span data-ttu-id="d64e4-150">Il file IProgressObserver.h file implementa un osservatore dello stato di avanzamento (vedere il [codice completo](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1263700592)).</span><span class="sxs-lookup"><span data-stu-id="d64e4-150">The IProgressObserver.h file implements a progress observer ([see complete code](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1263700592)).</span></span> <span data-ttu-id="d64e4-151">L'osservatore riceve notifica dello stato di avanzamento del download e dell'installazione (specificato come `char` senza segno, da 0 a 255, che indica il completamento dall'1% al 100%).</span><span class="sxs-lookup"><span data-stu-id="d64e4-151">This observer gets notified of download and installation progress (specified as an unsigned `char`, 0-255, indicating 1%-100% complete).</span></span> <span data-ttu-id="d64e4-152">L'osservatore riceve anche la notifica dell'invio di un messaggio da parte del chainer e invia una risposta.</span><span class="sxs-lookup"><span data-stu-id="d64e4-152">The observer is also notified when the chainee sends a message, and the observer should send a response.</span></span>

    ```cpp
        class IProgressObserver
        {
        public:
            virtual void OnProgress(unsigned char) = 0; // 0 - 255:  255 == 100%
            virtual void Finished(HRESULT) = 0;         // Called when operation is complete
            virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength) = 0; // Called when a message is sent
        };
    ```

#### <a name="chainingdotnet45cpp"></a><span data-ttu-id="d64e4-153">ChainingdotNet4.5.cpp</span><span class="sxs-lookup"><span data-stu-id="d64e4-153">ChainingdotNet4.5.cpp</span></span>

- <span data-ttu-id="d64e4-154">Il file [ChainingdotNet4.5.cpp](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1757268882) implementa la classe `Server`, derivata dalla classe `MmioChainer` ed esegue l'override dei metodi appropriati per visualizzare le informazioni sullo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="d64e4-154">The [ChainingdotNet4.5.cpp](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1757268882) file implements the `Server` class, which derives from the `MmioChainer` class and overrides the appropriate methods to display progress information.</span></span> <span data-ttu-id="d64e4-155">MmioChainer crea una sezione con il nome specificato e inizializza il chainer con il nome dell'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="d64e4-155">The MmioChainer creates a section with the specified section name and initializes the chainer with the specified event name.</span></span> <span data-ttu-id="d64e4-156">Il nome dell'evento viene salvato nella struttura dei dati mappata.</span><span class="sxs-lookup"><span data-stu-id="d64e4-156">The event name is saved in the mapped data structure.</span></span> <span data-ttu-id="d64e4-157">Specificare nomi di sezione ed evento univoci.</span><span class="sxs-lookup"><span data-stu-id="d64e4-157">You should make the section and event names unique.</span></span> <span data-ttu-id="d64e4-158">La classe `Server` nel codice seguente avvia il programma di installazione specificato, esegue il monitoraggio dello stato di avanzamento e restituisce un codice di uscita.</span><span class="sxs-lookup"><span data-stu-id="d64e4-158">The `Server` class in the following code launches the specified setup program, monitors its progress, and returns an exit code.</span></span>

    ```cpp
    class Server : public ChainerSample::MmioChainer, public ChainerSample::IProgressObserver
    {
    public:
        …………….
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName") //customize for your event names
        {}
    ```

    <span data-ttu-id="d64e4-159">L'installazione viene avviata nel metodo Main.</span><span class="sxs-lookup"><span data-stu-id="d64e4-159">The installation is started in the Main method.</span></span>

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

- <span data-ttu-id="d64e4-160">Prima di avviare l'installazione, il chainer verifica se .NET Framework 4.5 è già installato eseguendo una chiamata a `IsNetFx4Present`:</span><span class="sxs-lookup"><span data-stu-id="d64e4-160">Before launching the installation, the chainer checks to see if the .NET Framework 4.5 is already installed by calling `IsNetFx4Present`:</span></span>

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

- <span data-ttu-id="d64e4-161">È possibile modificare il percorso del file eseguibile (Setup.exe nell'esempio) nel metodo `Launch` per puntare alla posizione corretta oppure personalizzare il codice per determinare la posizione.</span><span class="sxs-lookup"><span data-stu-id="d64e4-161">You can change the path of the executable (Setup.exe in the example) in the `Launch` method to point to its correct location, or customize the code to determine the location.</span></span> <span data-ttu-id="d64e4-162">La classe di base `MmioChainer` offre un metodo `Run()` di blocco chiamato dalla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d64e4-162">The `MmioChainer` base class provides a blocking `Run()` method that the derived class calls.</span></span>

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

- <span data-ttu-id="d64e4-163">Il metodo `Send` intercetta ed elabora i messaggi.</span><span class="sxs-lookup"><span data-stu-id="d64e4-163">The `Send` method intercepts and processes the messages.</span></span> <span data-ttu-id="d64e4-164">In questa versione di .NET Framework l'unico messaggio supportato è il messaggio di chiusura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d64e4-164">In this version of the .NET Framework, the only supported message is the close application message.</span></span>

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

- <span data-ttu-id="d64e4-165">I dati dello stato di avanzamento sono costituiti da un `char` senza segno compreso tra 0 (0%) e 255 (100%).</span><span class="sxs-lookup"><span data-stu-id="d64e4-165">Progress data is an unsigned `char` between 0 (0%) and 255 (100%).</span></span>

    ```cpp
    private: // IProgressObserver
        virtual void OnProgress(unsigned char ubProgressSoFar)
        {…………
       }
    ```

- <span data-ttu-id="d64e4-166">HRESULT viene passato al metodo `Finished`.</span><span class="sxs-lookup"><span data-stu-id="d64e4-166">The HRESULT is passed to the `Finished` method.</span></span>

    ```cpp
    virtual void Finished(HRESULT hr)
    {
    // This HRESULT is communicated over MMIO and may be different than process
    // Exit code of the Chainee Setup.exe itself
    printf("\r\nFinished HRESULT: 0x%08X\r\n", hr);
    }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="d64e4-167">Il programma ridistribuibile .NET Framework 4.5 scrive in genere molti messaggi sullo stato di avanzamento e un unico messaggio per indicarne il completamento (sul lato del chainer).</span><span class="sxs-lookup"><span data-stu-id="d64e4-167">The .NET Framework 4.5 redistributable typically writes many progress messages and a single message that indicates completion (on the chainer side).</span></span> <span data-ttu-id="d64e4-168">La lettura viene eseguita in modo asincrono cercando i record `Abort`.</span><span class="sxs-lookup"><span data-stu-id="d64e4-168">It also reads asynchronously, looking for `Abort` records.</span></span> <span data-ttu-id="d64e4-169">Se viene ricevuto un record `Abort`, l'installazione viene annullata e il programma scrive un record completato con i dati E_ABORT dopo che l'installazione è stata interrotta ed è stato eseguito il rollback delle operazioni di installazione.</span><span class="sxs-lookup"><span data-stu-id="d64e4-169">If it receives an `Abort` record, it cancels the installation, and writes a finished record with E_ABORT as its data after the installation has been aborted and setup operations have been rolled back.</span></span>

<span data-ttu-id="d64e4-170">Un server tipico crea un nome file MMIO casuale, crea il file (come illustrato nell'esempio di codice precedente in `Server::CreateSection`) e avvia il programma ridistribuibile usando il metodo `CreateProcess` e passando il nome pipe con l'opzione `-pipe someFileSectionName`.</span><span class="sxs-lookup"><span data-stu-id="d64e4-170">A typical server creates a random MMIO file name, creates the file (as shown in the previous code example, in `Server::CreateSection`), and launches the redistributable by using the `CreateProcess` method and passing the pipe name with the `-pipe someFileSectionName` option.</span></span> <span data-ttu-id="d64e4-171">Il server deve implementare il metodi `OnProgress`, `Send` e `Finished` con il codice specifico dall'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d64e4-171">The server should implement `OnProgress`, `Send`, and `Finished` methods with application UI-specific code.</span></span>

## <a name="see-also"></a><span data-ttu-id="d64e4-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d64e4-172">See also</span></span>

- [<span data-ttu-id="d64e4-173">Guida alla distribuzione per gli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="d64e4-173">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)
- [<span data-ttu-id="d64e4-174">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="d64e4-174">Deployment</span></span>](index.md)
