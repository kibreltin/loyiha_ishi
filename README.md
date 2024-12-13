# loyiha_ishi
malumotlar bazasi fanidan
CREATE TABLE Hodisalar (
    Hodisa_ID INT PRIMARY KEY,
    Hodisa_sanasi DATE,
    Hodisa_vaqti TIME,
    Hodisa_joyi VARCHAR(255),
    Transport_turi VARCHAR(100),
    Hodisa_sababi VARCHAR(255)
);

CREATE TABLE Ishtirokchilar (
    Ishtirokchi_ID INT PRIMARY KEY,
    Hodisa_ID INT,
    Ishtirokchi_nomi VARCHAR(255),
    Ishtirokchi_turi VARCHAR(100),
    Yaralanganlik BOOLEAN,
    Halok_bolganlik BOOLEAN,
    FOREIGN KEY (Hodisa_ID) REFERENCES Hodisalar(Hodisa_ID)
);

CREATE TABLE Transport_Vositalari (
    Transport_ID INT PRIMARY KEY,
    Hodisa_ID INT,
    Transport_marka VARCHAR(255),
    Transport_raqami VARCHAR(50),
    Transport_turi VARCHAR(100),
    FOREIGN KEY (Hodisa_ID) REFERENCES Hodisalar(Hodisa_ID)
);
