-- phpMyAdmin SQL Dump
-- version 5.2.1
-- https://www.phpmyadmin.net/
--
-- Servidor: 127.0.0.1:3306
-- Tiempo de generación: 08-03-2024 a las 22:13:46
-- Versión del servidor: 8.0.35
-- Versión de PHP: 8.2.13

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Base de datos: `activity7`
--

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `course`
--

DROP TABLE IF EXISTS `course`;
CREATE TABLE IF NOT EXISTS `course` (
  `course_id` bigint NOT NULL AUTO_INCREMENT,
  `course_name` varchar(50) NOT NULL,
  `course_cover` varchar(50) NOT NULL,
  `content` varchar(50) NOT NULL,
  `robotics_kit_id` bigint NOT NULL,
  PRIMARY KEY (`course_id`),
  KEY `robotics_kit_id` (`robotics_kit_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `roboticskit`
--

DROP TABLE IF EXISTS `roboticskit`;
CREATE TABLE IF NOT EXISTS `roboticskit` (
  `robotics_kit_id` bigint NOT NULL AUTO_INCREMENT,
  `robotics_kit_name` varchar(50) NOT NULL,
  PRIMARY KEY (`robotics_kit_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `role`
--

DROP TABLE IF EXISTS `role`;
CREATE TABLE IF NOT EXISTS `role` (
  `role_id` bigint NOT NULL,
  `role_name` varchar(30) NOT NULL,
  KEY `role_id` (`role_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `user`
--

DROP TABLE IF EXISTS `user`;
CREATE TABLE IF NOT EXISTS `user` (
  `user_id` bigint NOT NULL AUTO_INCREMENT,
  `name` varchar(50) NOT NULL,
  `email` varchar(50) NOT NULL,
  `role_id` bigint NOT NULL,
  PRIMARY KEY (`user_id`),
  KEY `role_id` (`role_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

--
-- Restricciones para tablas volcadas
--

--
-- Filtros para la tabla `course`
--
ALTER TABLE `course`
  ADD CONSTRAINT `course_ibfk_1` FOREIGN KEY (`robotics_kit_id`) REFERENCES `roboticskit` (`robotics_kit_id`) ON DELETE CASCADE ON UPDATE CASCADE;

--
-- Filtros para la tabla `role`
--
ALTER TABLE `role`
  ADD CONSTRAINT `role_ibfk_1` FOREIGN KEY (`role_id`) REFERENCES `user` (`role_id`) ON DELETE CASCADE ON UPDATE CASCADE;
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;



--------------------- HOMEWORK 6 -------------------------
# Project Name

This project is a Laravel application for managing a robotics school. It includes features such as user authentication, course management, and enrollment of students in different groups.
# Robotics School Management System

This project is a Laravel application for managing a robotics school. It includes features such as user authentication, course management, and enrollment of students in different groups.

## ER Diagram

![ER Diagram](/diagramERHomework6.png)

