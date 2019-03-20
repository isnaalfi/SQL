-- phpMyAdmin SQL Dump
-- version 4.0.4.1
-- http://www.phpmyadmin.net
--
-- Host: 127.0.0.1
-- Generation Time: Nov 21, 2017 at 06:34 PM
-- Server version: 5.5.32
-- PHP Version: 5.4.19

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8 */;

--
-- Database: `db`
--
CREATE DATABASE IF NOT EXISTS `db` DEFAULT CHARACTER SET latin1 COLLATE latin1_swedish_ci;
USE `db`;

-- --------------------------------------------------------

--
-- Table structure for table `asset`
--

CREATE TABLE IF NOT EXISTS `asset` (
  `ID_WP` varchar(9) NOT NULL,
  `Mobil` int(2) NOT NULL,
  `Tanah` int(2) NOT NULL,
  `Saham` int(2) NOT NULL,
  `Total` int(5) DEFAULT NULL,
  PRIMARY KEY (`ID_WP`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `asset`
--

INSERT INTO `asset` (`ID_WP`, `Mobil`, `Tanah`, `Saham`, `Total`) VALUES
('PN2011003', 0, 1, 0, NULL),
('PS1990002', 1, 1, 0, NULL),
('PS1993005', 2, 1, 1, NULL),
('WN2001004', 3, 2, 2, NULL),
('WS1996006', 1, 1, 1, NULL),
('WS2016001', 1, 0, 0, NULL);

-- --------------------------------------------------------

--
-- Table structure for table `pajak_asset`
--

CREATE TABLE IF NOT EXISTS `pajak_asset` (
  `Jenis` varchar(5) NOT NULL,
  `Harga(jt)` int(3) NOT NULL,
  `Pajak(%)` int(3) NOT NULL,
  PRIMARY KEY (`Jenis`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `pajak_asset`
--

INSERT INTO `pajak_asset` (`Jenis`, `Harga(jt)`, `Pajak(%)`) VALUES
('Mobil', 100, 5),
('Saham', 120, 18),
('Tanah', 200, 15);

-- --------------------------------------------------------

--
-- Table structure for table `pajak_per_tahun`
--

CREATE TABLE IF NOT EXISTS `pajak_per_tahun` (
  `ID_WP` varchar(9) NOT NULL,
  `Gaji(juta)` int(5) NOT NULL,
  `Total_Aset(juta)` int(5) DEFAULT NULL,
  `Total_Pajak(juta)` int(5) DEFAULT NULL,
  PRIMARY KEY (`ID_WP`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `pajak_per_tahun`
--

INSERT INTO `pajak_per_tahun` (`ID_WP`, `Gaji(juta)`, `Total_Aset(juta)`, `Total_Pajak(juta)`) VALUES
('PN2011003', 20, NULL, NULL),
('PS1990002', 30, NULL, NULL),
('PS1993005', 100, NULL, NULL),
('WN2001004', 70, NULL, NULL),
('WS1996006', 34, NULL, NULL),
('WS2016001', 25, NULL, NULL);

-- --------------------------------------------------------

--
-- Table structure for table `wajib_pajak`
--

CREATE TABLE IF NOT EXISTS `wajib_pajak` (
  `ID_WP` varchar(9) NOT NULL,
  `Nama` varchar(25) NOT NULL,
  `Tanggal_Lahir` date NOT NULL,
  `Nama_Jalan` varchar(30) NOT NULL,
  `Nama_Kota` varchar(15) NOT NULL,
  PRIMARY KEY (`ID_WP`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `wajib_pajak`
--

INSERT INTO `wajib_pajak` (`ID_WP`, `Nama`, `Tanggal_Lahir`, `Nama_Jalan`, `Nama_Kota`) VALUES
('PN2011003', 'Clint Barton', '1975-04-21', 'Huntington Avenue', 'Boston'),
('PS1990002', 'Clark Kent', '1988-02-27', 'East Main St', 'Rochester'),
('PS1993005', 'Jimmy Olsen', '1996-02-28', 'Federal St', 'Boston'),
('WN2001004', 'Natasha Romanoff', '1978-08-09', 'Girard Avenue', 'Philadelphia'),
('WS1996006', 'Andreas Rojas', '1984-10-21', 'East Main St', 'Rochester'),
('WS2016001', 'Peggy Carter', '2000-08-06', 'Bellona Avenue', 'Baltimore');

--
-- Constraints for dumped tables
--

--
-- Constraints for table `asset`
--
ALTER TABLE `asset`
  ADD CONSTRAINT `asset_ibfk_1` FOREIGN KEY (`ID_WP`) REFERENCES `wajib_pajak` (`ID_WP`);

--
-- Constraints for table `pajak_per_tahun`
--
ALTER TABLE `pajak_per_tahun`
  ADD CONSTRAINT `pajak_per_tahun_ibfk_1` FOREIGN KEY (`ID_WP`) REFERENCES `wajib_pajak` (`ID_WP`);

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
