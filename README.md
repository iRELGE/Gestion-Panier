# Gestion-Panier
Gestion panier webForm asp.net
Script SQL:
CREATE TABLE [dbo].[Legume] (
    [IdLegume] INT           NOT NULL,
    [Libelle]  VARCHAR (50)  NULL,
    [Prix]     FLOAT (53)    NULL,
    [Image]    VARCHAR (200) NULL,
    PRIMARY KEY CLUSTERED ([IdLegume] ASC)
);
////////////////////////////////
CREATE TABLE [dbo].[Panier] (
    [IdPanier] INT          NOT NULL,
    [Couleur]  VARCHAR (10) NULL,
    [Taille]   VARCHAR (10) NULL,
    PRIMARY KEY CLUSTERED ([IdPanier] ASC)
);

/////////////////////////////:
CREATE TABLE [dbo].[Panier_Legume] (
    [IdPanier] INT NOT NULL,
    [IdLegume] INT NOT NULL,
    [Quantite] INT NULL,
    PRIMARY KEY CLUSTERED ([IdPanier] ASC, [IdLegume] ASC),
    CONSTRAINT [FK_PanierLegume_Legume] FOREIGN KEY ([IdLegume]) REFERENCES [dbo].[Legume] ([IdLegume]),
    CONSTRAINT [FK_PanierLegume_Panier] FOREIGN KEY ([IdPanier]) REFERENCES [dbo].[Panier] ([IdPanier])
);

