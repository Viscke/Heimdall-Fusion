Heimdall Fusion é um framework monolítico de auditoria de segurança projetado para simular o ciclo de vida completo de um ataque cibernético avançado (APT). Ele atua como um "Observador Absoluto", capaz de romper parâmetros físicos sem fio (Wi-Fi), pivotar para a rede interna e orquestrar um reconhecimento profundo desde a camada de enlace (L2) até a camada de aplicação (L7).
Desenvolvido com foco em alta performance e evasão, o Heimdall otimiza o hardware do hospedeiro (I/O via RAM Disk e paralelismo extremo) para realizar testes de estresse, mapeamento de Active Directory e varredura de vulnerabilidades (CVEs), entregando as evidências em um cofre criptografado.

Principais funções:

Infiltração de Perímetro (Wireless)
WPA2/WPA3 Quick Crack: Captura autônoma de PMKID e Handshakes com tentativa de quebra offline em tempo hábil.
WPS Pixie-Dust: Exploração de falhas estruturais em roteadores legados.
Captive Portal Sequestration (Evil Twin): Clonagem de AP, sequestro de DNS (Dnsmasq) e engenharia social via servidor HTTP interativo para captura de PSK.

Evasão e Stealth Operacional
MAC Spoofing Global: Camuflagem de identidade em todas as interfaces de rede.
Volatilidade (Disco RAM): Execução de I/O massiva em /dev/shm (Memória RAM), não deixando artefatos no disco rígido do hospedeiro.
Nmap Idle Scan (Zombie Host): Mapeamento de rede utilizando máquinas ociosas como "laranjas" para roubar sistemas de IDS/IPS corporativos.

Reconhecimento Massivo e Interrogação (L3-L7)
Descoberta Híbrida: Integração de Masscan e Zmap para varredura de portas em altíssima velocidade.
Ondas Curtas e IPv6: Escuta passiva de dispositivos Bluetooth Low Energy (BLE) e descoberta de hosts via IPv6 Multicast (Ping ff02::1).
Mapeamento do Active Directory: Enumeração automática de compartilhamentos SMB e remoção de topologia para o BloodHound via NetExec.
Web Fuzzing & Visual Recon: Captura de telas de painéis administrativos (gowitness) e descoberta de diretórios/chaves na nuvem (ffuf).

Motor de Vulnerabilidades & C2
Next-Gen Scanner: Integração com Núcleos para detecção de CVEs, painéis expostos e falhas de configuração.
Out-of-Band (OOB): Validação de falhas cegas (Blind RCE/SSRF) utilizando interações via Interactsh.
Telemetria (C2): Alertas em tempo real enviados via Telegram em caso de descoberta de vulnerabilidades críticas.

Retenção de Evidências Corporativas
Data Lake Local: Compilação dos resultados em um banco de dados SQLite estruturado, ideal para entrada em plataformas de Zero Trust e Firewalls.
Selo Criptográfico: Todos os arquivos de configuração, credenciais (tshark), capturas de rede (tcpdump) e relatórios são compactados e criptografados no padrão AES-256-CBC.

Arquitetura e Desempenho
O Heimdall foi arquitetado como um roteiro monolítico, eliminando atritos de implantação. Ele ajusta dinamicamente as configurações do Kernel Linux (sysctl) para suportar altíssima concorrência (problema C10k) e evitar a exaustão de portas TCP e limite de arquivos abertos, garantindo que o hardware seja utilizado em seu limite sem causar Kernel Panic.

Aviso Legal (Isenção de Responsabilidade)
Este projeto foi desenvolvido exclusivamente para fins de auditoria profissional autorizada. O uso desta ferramenta em redes, sistemas ou infraestruturas que você não possui, ou sem consentimento explícito e por escrito dos proprietários, é proibido e ilegal. O desenvolvedor não assume nenhuma responsabilidade pelo uso indevido deste software.
Construído para não deixar pontos cegos.
